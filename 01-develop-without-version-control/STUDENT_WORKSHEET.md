# Activity 1 Student Worksheet

You receive two independently changed files:

- `student_file_a.cpp` validates score ranges.
- `student_file_b.cpp` displays the highest score.

Create `combined.cpp` with both features. Do not use Git or an automatic comparison/merge tool.

## Compare and combine

| File | Feature present | Important changed lines |
|---|---|---|
| `student_file_a.cpp` | 11 | 14 |
| `student_file_b.cpp` |1  | 13 |16|

| Input | Actual output | Pass/fail |
|---|---|---|
| `70 80 90` | 80.0 | 90.0 |pass|
| `-1 80 90` | fail | pass |
| `70 101 90` | fial | pass |

## From experience to requirements

**Observation — what actually happened while you worked:**

_when one replace another the validation will disappeared__

**Problem — why that event could cause harm:**

__that could be a problem because you'll lose the work___

**UN:** A developer needs a way to _combine independent changes

because _replacing a file can cause valid work to be destroyed.

**UR:** A developer shall be able to __notice the chages in each files before combining changes.

## Example

If a student copies all of File B over File A, Task A disappears.

- Observation: “The validation code disappeared after one file replaced the other.”
- Problem: “Valid work can be lost when complete files replace one another.”
- UN: “A developer needs a way to combine independent changes because replacing complete files can destroy valid work.”
- UR: “A developer shall be able to identify the content changed in each file before combining the changes.”

