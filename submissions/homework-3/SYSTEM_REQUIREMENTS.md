
# Homework 3 — System Requirements and Verification
## Approved User Need (UN) Baseline
- UN-GIT-01: A student developer needs a way to start tracking a local project because it has no recorded history.
- UN-GIT-02: A student developer needs to know which project files have changed because they may forget what they edited before recording a checkpoint.
- UN-GIT-03: A student developer needs to inspect changed content before recording it because a file may contain unintended edits.
- UN-GIT-04: A student developer needs to choose the file content to include in the next checkpoint because some current changes may still be unfinished.
- UN-GIT-05: A student developer needs to record a meaningful checkpoint because they want to record an important project version and provide a descriptive label.
- UN-GIT-06: A student developer needs to review earlier checkpoints because they want to understand how the project reached its current state.
- UN-GIT-07: A student developer needs invalid commands to fail while preserving existing project files and recorded checkpoints.
## Approved User Requirement (UR) Baseline
- UR-GIT-01: A student developer shall be able to initialize tracking in the current local project folder without removing existing project files.
- UR-GIT-02: A student developer shall be able to see whether project files are untracked, staged, changed after staging, modified, deleted, or clean.
- UR-GIT-03: A student developer shall be able to view differences between current working file content and the content selected for the next checkpoint.
- UR-GIT-04: A student developer shall be able to view differences between content selected for the next checkpoint and the latest recorded checkpoint.
- UR-GIT-05: A student developer shall be able to select the current content of one existing project file for the next checkpoint without selecting unrelated files.
- UR-GIT-06: A student developer shall be able to create a checkpoint of selected content with a nonempty explanation while leaving later unselected edits in the working files.
- UR-GIT-07: A student developer shall be able to view recorded checkpoints from newest to oldest, including their identifier and explanation.
- UR-GIT-08: A student developer shall receive a useful error when a command is invalid, a requested file is unavailable, or a path is outside the allowed project files.
- UR-GIT-09: A student developer shall be able to retry an operation after a failure without losing ordinary project files or an already recorded checkpoint.
## Functional System Requirements
### SR-01 — Initialize a project
The system shall initialize tracking in the current local project folder when tracking has not already been initialized, while preserving all existing project files.
Source UR: UR-GIT-01
Check: Run `init` in a project containing existing files and verify that the files remain present and tracking is initialized.
### SR-02 — Reinitialize an existing project
The system shall leave the existing tracking state and project files intact when `init` is run on an already initialized project.
Source UR: UR-GIT-01, UR-GIT-09
Check: Run `init` twice and verify that the second operation does not remove or alter existing project files or recorded checkpoints.
### SR-03 — Report project file states
The system shall report whether project files are untracked, staged, modified, deleted, or clean when `status` is requested.
Source UR: UR-GIT-02
Check: Run `status` after creating, modifying, staging, and deleting files and verify that the reported states match the project state.
### SR-04 — Report an individual staged file
The system shall show the staged state of an existing project file when `status` is requested after that file has been selected.
Source UR: UR-GIT-02
Check: Stage one existing file, run `status`, and verify that the file is identified as staged.
### SR-05 — Show working-file differences
The system shall display the content differences between the current working file and the content selected for the next checkpoint when `diff` is requested.
Source UR: UR-GIT-03
Check: Modify a file after selecting earlier content and run `diff`; verify that the output identifies the changed content.
### SR-06 — Select one existing file
The system shall select the current content of one existing project file when `add <file>` is requested, without selecting unrelated files.
Source UR: UR-GIT-05
Check: Run `add calculator.cpp` and verify that only `calculator.cpp` is selected for the next checkpoint.
### SR-07 — Reject an unavailable file
The system shall display a useful error and preserve the current project state when `add <file>` is requested for a missing or unavailable file.
Source UR: UR-GIT-08, UR-GIT-09
Check: Run `add missing.txt` and verify that an error is shown and previously existing files and selected content remain unchanged.
### SR-08 — Show selected-content differences
The system shall display the differences between selected content and the latest recorded checkpoint when `diff --staged` is requested.
Source UR: UR-GIT-04
Check: Select a changed file, run `diff --staged`, and verify that the output compares the selected content with the latest checkpoint.
### SR-09 — Require a checkpoint explanation
The system shall reject a checkpoint request that does not contain a nonempty explanation.
Source UR: UR-GIT-06, UR-GIT-08
Check: Attempt `commit` without a nonempty explanation and verify that an error is displayed and no new checkpoint is recorded.
### SR-10 — Record selected content
The system shall create a new numbered checkpoint containing the selected file content when `commit` is requested with a nonempty explanation.
Source UR: UR-GIT-06
Check: Select one file, run `commit` with an explanation, and verify that a new numbered checkpoint is created containing the selected content.
### SR-11 — Preserve unselected edits
The system shall leave later unselected working-file edits unchanged after a successful checkpoint is created.
Source UR: UR-GIT-06, UR-GIT-05
Check: Make a later edit to an unselected file, create a checkpoint, and verify that the later edit remains in the working file.
### SR-12 — Display checkpoint history
The system shall display recorded checkpoints from newest to oldest, including each checkpoint identifier and explanation, when `log` is requested.
Source UR: UR-GIT-07
Check: Create at least two checkpoints, run `log`, and verify that the newest checkpoint appears before the older checkpoint and both identifiers and explanations are shown.
### SR-13 — Reject invalid commands
The system shall display a useful error and preserve the existing project state when an unsupported command is requested.
Source UR: UR-GIT-08, UR-GIT-09
Check: Run an invalid command and verify that an error is displayed and existing project files and checkpoints remain unchanged.
### SR-14 — Reject paths outside the project
The system shall display a useful error when an operation requests a path outside the allowed project files.
Source UR: UR-GIT-08
Check: Request an operation using a path outside the project and verify that the system reports an error without changing project files or checkpoints.



