
# Static Code Verification — Review Checklist

**Source File:** `game.cpp`  
**Review Type:** Static Code Verification

| Category | Defect | Result (Issue/OK) |
|---|---|---|
| Initialization | `sum` in `averageAttack()` is not initialized before use (line 87). | Issue |
| Pointers (null/delete) | `attackMonster()` and `getMonsterLabel()` may dereference null pointers. `defeatMonster()` accesses a pointer after deletion. `readBoss()` uses incorrect deallocation, and `bonus` is never deleted. | Issue |
| Arrays / Buffers | `spawnMonster()` does not check array capacity. Six monsters are spawned although `MAX_MONSTERS` is 5. `readBoss()` allows unbounded input into a 10-byte buffer. | Issue |
| Loops | `totalMonsterHealth()` uses `i <= monsterCount`, causing an out-of-bounds access. | Issue |
| Arithmetic | `attackMonster()` mixes signed and unsigned arithmetic, making its health check ineffective. `averageAttack()` may divide by zero. `calculateDamage()` uses integer arithmetic. | Issue |
| Control Flow | `findMonster()` uses assignment (`=`) instead of comparison (`==`). `playerRank()` does not return a value for scores less than or equal to 100. | Issue |
| Function/Call | Functions do not safely handle a monster ID that is not found. `spawnMonster()` does not prevent spawning beyond capacity. | Issue |
| Classes | `Game` has raw owning pointers but no proper copy constructor or assignment operator. Copying the object can cause double deletion. `defeatMonster()` leaves a dangling pointer in the array. | Issue |

## Checklist Conclusion

**Overall Result: Issues Found**

The source code contains memory-management defects, array-boundary errors, incorrect logic, and missing return behavior. Refer to `code_review_report.md` for detailed findings and proposed solutions.

