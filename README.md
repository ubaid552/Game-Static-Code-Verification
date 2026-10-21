
# Static Code Verification and Code Review

![Language](https://img.shields.io/badge/Language-C%2B%2B-blue)
![Documentation](https://img.shields.io/badge/Documentation-Markdown-blue)
![Review Type](https://img.shields.io/badge/Review-Static%20Analysis-orange)
![Status](https://img.shields.io/badge/Status-Review%20Completed-success)

## Table of Contents

- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Scope of Verification](#scope-of-verification)
- [Review Methodology](#review-methodology)
- [Project Structure](#project-structure)
- [Review Categories](#review-categories)
- [Defect Classification](#defect-classification)
- [Tools and Technologies](#tools-and-technologies)
- [How to Use This Repository](#how-to-use-this-repository)
- [Expected Outcomes](#expected-outcomes)
- [Limitations](#limitations)
- [Conclusion](#conclusion)
- [Author](#author)

## Introduction

Static Code Verification is an important activity in Software Verification and Validation (SVV). It involves examining source code to identify programming defects, logical errors, unsafe operations, and potential reliability issues without executing the program.

This project presents a manual static code review of a C++ source file named `game.cpp`. The review uses a structured checklist and a detailed code review report to document identified defects, explain their impact, and recommend possible solutions.

## Project Overview

The purpose of this project is to evaluate the quality and safety of the supplied C++ source code through systematic inspection.

The verification process focuses on common programming errors, including incorrect conditional statements, pointer misuse, array boundary violations, arithmetic problems, memory management errors, and issues involving classes and functions.

The findings are documented in two Markdown files:

- **Review Checklist:** Provides a category-wise summary of the inspection.
- **Code Review Report:** Records individual defects, their locations, explanations, proposed solutions, and severity ratings.

This project demonstrates how a structured code review can help developers identify potential defects before executing or deploying a program.

## Objectives

The main objectives of this project are:

- To understand the purpose of static code verification.
- To inspect C++ source code without executing it.
- To identify programming defects and potential runtime errors.
- To evaluate code using a standardized review checklist.
- To document defects with their corresponding line numbers.
- To explain the consequences of identified defects.
- To recommend appropriate corrective actions.
- To classify defects according to their severity.
- To improve awareness of secure and reliable programming practices.

## Scope of Verification

The review covers the following aspects of the source code:

- Variable initialization and use.
- Pointer validity and memory deallocation.
- Array boundaries and buffer handling.
- Loop conditions and iteration limits.
- Arithmetic operations and data type conversions.
- Conditional statements and control flow.
- Function calls, parameters, and return values.
- Class design, object copying, and resource ownership.

The review is based on the supplied source code and focuses on defects that can be identified through manual inspection.

## Review Methodology

The following steps describe the review process.

### Step 1: Source Code Inspection

The C++ source file is examined to understand its structure, functions, variables, classes, and memory management.

### Step 2: Checklist-Based Review

The source code is reviewed against eight predefined categories. Each category is marked as `Issue` or `OK`, and identified defects are briefly documented.

### Step 3: Defect Identification

Potential defects are located and classified according to their type, such as pointer errors, array boundary violations, arithmetic errors, or incorrect control flow.

### Step 4: Impact Analysis

Each defect is examined to understand how it could affect program behavior, memory safety, reliability, or correctness.

### Step 5: Proposed Solutions

A recommended corrective action is documented for each identified defect.

### Step 6: Severity Assessment

Each defect is assigned a severity level based on its potential impact.

### Step 7: Documentation

The results are recorded in the review checklist and detailed code review report.

## Project Structure

The repository is organized as follows:

```text
cpp-static-code-verification/
│
├── game.cpp
├── review_checklist.md
├── code_review_report.md
└── README.md
```

### File Descriptions

| File | Description |
|---|---|
| `game.cpp` | C++ source file being reviewed. |
| `review_checklist.md` | Checklist containing eight review categories, defects, and results. |
| `code_review_report.md` | Detailed findings, line numbers, explanations, proposed solutions, and severity ratings. |
| `README.md` | Project introduction, methodology, documentation, and usage instructions. |

## Review Categories

The code is inspected using the following eight categories.

### 1. Initialization

Checks whether variables are initialized before use and whether values are valid when accessed.

### 2. Pointers (null/delete)

Checks for null-pointer dereferences, invalid memory access, incorrect deletion, memory leaks, and use-after-free.

### 3. Arrays / Buffers

Checks array capacity, index boundaries, input handling, and potential buffer overflow.

### 4. Loops

Checks loop conditions, iteration limits, and possible out-of-bounds access.

### 5. Arithmetic

Checks arithmetic operations, signed and unsigned conversions, division by zero, and unintended integer calculations.

### 6. Control Flow

Checks conditional expressions, assignment-versus-comparison mistakes, and missing return paths.

### 7. Function/Call

Checks function parameters, return values, error handling, and behavior when requested objects cannot be found.

### 8. Classes

Checks class design, object copying, ownership of dynamically allocated memory, and resource-management behavior.

## Defect Classification

Defects are recorded using the following severity levels.

| Severity | Description |
|---|---|
| Critical | A defect that may lead to severe memory-safety problems, memory corruption, or serious program failure. |
| High | A defect that may significantly affect correctness, reliability, or safe execution. |
| Medium | A defect that may cause incorrect results or resource-management issues under particular conditions. |
| Low | A minor defect with limited impact on program behavior or maintainability. |

Severity ratings are assigned during the review according to the potential impact of each finding.

## Tools and Technologies

The project uses the following technologies and techniques:

- **C++:** Programming language of the source code under review.
- **Markdown:** Format used to document the checklist and review findings.
- **Git:** Version control for tracking project files and changes.
- **GitHub:** Repository hosting and project documentation.
- **Manual Static Review:** Source inspection without executing the program.

No automated static-analysis tool or compiler-based verification is claimed as part of this review.

## How to Use This Repository

1. Clone or download the repository.
2. Open `game.cpp` in a code editor.
3. Read `review_checklist.md` for the category-wise review results.
4. Read `code_review_report.md` for the detailed defect descriptions and recommended fixes.
5. Compare the findings with the corresponding source code.
6. Apply proposed corrections if required.
7. Compile and test the corrected program separately to validate the changes.

### Clone the Repository

Replace `YOUR_USERNAME` with your GitHub username and `YOUR_REPOSITORY` with your repository name.

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

## Expected Outcomes

After completing this task, the reviewer should be able to:

- Explain the purpose of static code verification.
- Identify common C++ programming defects.
- Understand pointer and memory-management risks.
- Recognize array boundary and buffer-handling problems.
- Evaluate arithmetic and control-flow logic.
- Prepare a structured code review checklist.
- Produce a detailed defect report with proposed solutions.
- Understand the importance of verification before program execution.

## Limitations

This project documents a manual static code review. The findings depend on the supplied source code and the scope of the inspection.

The review does not, by itself, prove that the program is free from defects. Compilation, dynamic testing, automated static analysis, and verification of applied fixes are separate activities and have not been claimed as completed.

Line numbers may change if the source code is modified.

## Conclusion

This project demonstrates a structured approach to static code verification for a C++ program. By examining initialization, pointers, arrays, loops, arithmetic, control flow, functions, and classes, the review identifies potential defects and documents corrective recommendations.

The checklist provides a concise overview, while the detailed report supports further investigation and correction. Together, these documents provide a foundation for improving code correctness, memory safety, and software reliability.

