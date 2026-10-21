
# Static Code Verification — Code Review Report

**Source File:** `game.cpp`  
**Review Type:** Static Code Verification

| Line Number | Defect Type | Why It Is a Problem | Proposed Solution | Severity |
|---|---|---|---|---|
| 51–52 | Missing capacity check | `spawnMonster()` writes beyond the array if `monsterCount` reaches `MAX_MONSTERS`. | Check `monsterCount < MAX_MONSTERS` before adding a monster. | Critical |
| 57 | Assignment instead of comparison | `monsters[i]->id = id` changes the monster ID instead of comparing it. | Replace `=` with `==`. | High |
| 64–66 | Null-pointer dereference | If `findMonster()` returns `nullptr`, accessing `m->health` causes undefined behavior. | Check `m == nullptr` before accessing the monster. | Critical |
| 65–66 | Signed/unsigned arithmetic | Negative damage converts to unsigned, making the health check incorrect. | Reject negative damage and use appropriate signed arithmetic. | High |
| 66–68 | Incorrect damage handling | The health check is ineffective and may allow incorrect health calculations. | Validate damage and set health to zero when damage exceeds current health. | High |
| 74–75 | Out-of-bounds array access | The loop uses `i <= monsterCount`, accessing an element outside the active range. | Change the condition to `i < monsterCount`. | Critical |
| 80–83 | Dangling reference | The function returns a reference to the local variable `label`, which is destroyed when the function returns. | Return `std::string` by value instead of `std::string&`. | Critical |
| 81–82 | Null-pointer dereference | If the monster is not found, accessing `m->id` and `m->name` is invalid. | Check whether `m` is null before using it. | Critical |
| 87–89 | Uninitialized variable | `sum` is used before initialization, producing an indeterminate result. | Initialize it with `double sum = 0.0;`. | High |
| 90 | Division by zero | `averageAttack()` divides by `monsterCount`, which may be zero. | Check whether `monsterCount == 0` before division. | High |
| 93–96 | Use-after-free | The code deletes `m` and then accesses `m->name`. | Print the name before deleting the monster. | Critical |
| 93–96 | Missing null check / stale pointer | A missing monster causes a null dereference. After deletion, the pointer remains in the array and the count is not updated. | Check for null, remove the monster from the array, and update `monsterCount`. | Critical |
| 101 | Unintended integer arithmetic | Integer multiplication and division occur before the result is converted to `double`. | Use floating-point arithmetic, such as `attack * (armorPercent / 100.0)`, if fractional damage is intended. | Medium |
| 104–109 | Missing return statement | `playerRank()` has no return value when `score <= 100`. | Add a final return statement for scores of 100 or less. | High |
| 112–115 | Buffer overflow | Input longer than the allocated buffer can overwrite memory. | Use `std::string` instead of a fixed-size character buffer. | Critical |
| 119 | Mismatched memory deallocation | Memory allocated using `new char[10]` is released using `delete` instead of `delete[]`. | Use `delete[] name`, or preferably replace the buffer with `std::string`. | High |
| 124–129 | Array capacity exceeded | Six monsters are spawned even though `MAX_MONSTERS` is 5. | Increase the capacity, limit the number of monsters, or use a dynamically sized container. | Critical |
| 131 | Memory leak | The `bonus` monster is dynamically allocated but never deleted. | Remove the unused allocation or manage it using `std::unique_ptr`. | Medium |
| 143 | Shallow copy / double deletion | `Game copy = game` copies raw pointer values. Both objects may delete the same monsters. | Implement safe deep copying or disable copying; alternatively, redesign ownership using smart pointers. | Critical |

## Overall Assessment

**Result: Issues Found — Corrections Required**

The highest-priority defects include unchecked array capacity, out-of-bounds access, null-pointer dereferences, dangling references, use-after-free, buffer overflow, and unsafe copying of the `Game` class.

**Scope Note:** This report is based on static inspection of the supplied source code. The program has not been claimed to have been compiled or dynamically tested.
