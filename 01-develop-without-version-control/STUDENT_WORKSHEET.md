# Activity 1 Student Worksheet

You receive two independently changed files:

- `student_file_a.cpp` validates score ranges.
- `student_file_b.cpp` displays the highest score.

Create `combined.cpp` with both features. Do not use Git or an automatic comparison/merge tool.

## Compare and combine

| File | Feature present | Important changed lines |
|---|---|---|
| `student_file_a.cpp` | 11 |14  |
| `student_file_b.cpp` | 1 | 13 |16|

| Input | Actual output | Pass/fail |
|---|---|---|
| `70 80 90` | 80.0 |90.0 |pass|
| `-1 80 90` | invalid score | fail |
| `70 101 90` | invalid score | fail |

## From experience to requirements

**Observation — what actually happened while you worked:**

__when a file replace another file the validation code disappears.
**Problem — why that event could cause harm:**

_that could cause a problem because the valid code will be lost_

**UN:** A developer needs a way to  to combine independent changes_

because _it can detroye a __valid work.

**UR:** A developer shall be able to ___________________________________.

## Example

If a student copies all of File B over File A, Task A disappears.

- Observation: “The validation code disappeared after one file replaced the other.”
- Problem: “Valid work can be lost when complete files replace one another.”
- UN: “A developer needs a way to combine independent changes because replacing complete files can destroy valid work.”
- UR: “A developer shall be able to identify the content changed in each file before combining the changes.”

