# Activity 2 Student Worksheet

Do not merely define a command. Explain what the user observes, wants, and risks.

| Command | What does the user observe? | What is the user trying to accomplish? | What problem or risk is addressed? |
|---|---|---|---|
| `status` | it let's you the current state of your project | to know which file as change before committing them | the developer might rest committing the wrong file |
| `diff` | the change that as been made in the file | review changes before committing them | to not commit the unwanted changes  |
| `add <file>` | selected files for the staging area  | selecting the changes they want to commit | to avoid adding the wrong change in the commit |
| `commit -m "message"` | new commit to be made with stage changes  | to save a version of the project | to avoid recording the wrong changes |
| `log` | user see the old commit | to too see the project history and the changes recorded | the problem is it could be hard to understand the changes in the project history |

Example for a non-Git command: A “print” command produces a paper copy; the user wants information usable away from the computer; the risk is lacking access during a meeting.

**UN-01:** A __Developer_ needs a way to _to understand the chages made in the project_

because _so they won't commit the wrong change_.

Evidence command(s): _git diff_

**UN-02:** A _developer_ needs a way to _select a file for staging_

because _to avoid committing an unchange file_.

Evidence command(s): _git add__

