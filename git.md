<image alt="Docker Logo" height="100px" src="./images/git.png" width="100px" />

# Git

* States
    * untracked - Not being tracked by Git.
    * staged - Marked for inclusion in the next commit.
    * committed - Saved to the repository's history.

## Git Commands

* `git status` - Shows the current state of your repo. It will tell you which files are untracked, staged, and committed.
* `git add <path/to/file | pattern>` - Adds directory or file to commit.
    * You can add multiple directories and file names as arguments to add to a commit.
* `git add .` - Adds all changed directories and files to commit.
* `git commit -m "your message"` - Add a message to your commit.
* `git log` - Shows a history of the commits in a repository.
    * Each commit has a unique identifier called a "commit hash".