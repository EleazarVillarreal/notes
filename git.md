<image alt="Docker Logo" height="100px" src="./images/git.png" width="100px" />

# Git

* States:
    * Untracked - Not being tracked by Git.
    * Staged - Marked for inclusion in the next commit.
    * Committed - Saved to the repository's history.
* Locations:
    * System: `/etc/gitconfig` - The file that configures Git for all users on the system.
    * Global: `~/.gitconfig` - The file that configures Git for all projects of a user
    * Local: `.git/config` -  The file that configures Git for a specific project
    * worktree: `.git/config.worktree` -  The file that configures Git for part of a project
* Tree - Git's way of storing a directory.
* Blob - Git's way of storying a file.

## Git Commands

* `git config` - Allows you to interact with your configuration.
    * Example: `git config --add --global user.name "Eleazar Villarreal"`
    * `--add` - States you want to add to your Git configuration.
    * `--global` - Stores your configuration globally in your `~/.gitconfig`. 
    * `--local` - Stores your configuration locally in your current repo only.
    * `--list` - Lets you see all configuration values.
    * `--get <key>` - Lets you see a single value.
    * `--unset <key>` - Removes a specific configuration value.
    * `--unset-all <key>` - Removes all instances of the specific configuration value.
    * `--remove-section` - Removes an entire section from your Git configuration.

* `git status` - Shows the current state of your repo. It will tell you which files are untracked, staged, and committed.
* `git add <path/to/file | pattern>` - Adds directory or file to commit.
    * You can add multiple directories and file names as arguments to add to a commit.
* `git add .` - Adds all changed directories and files to commit.
* `git commit -m "your message"` - Add a message to your commit.
* `git log` - Shows a history of the commits in a repository.
    * Each commit has a unique identifier called a "commit hash".
* `git cat-file -p <blob/commit/tree hash>` - Allows you to see the contents of a specific blob, commit, or tree and formats the output.