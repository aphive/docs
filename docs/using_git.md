Before proceeding, ensure that you have your SSH properly setup and configured, see the [Using SSH Keys](using_ssh_keys.md) tutorial to get this done.

## Installation

### Xcode
Install Xcode by runing this command in your terminal
```
xcode-select --install
```
### Homebrew
You should already have Homebrew installed, if not, check out my guide [here](using_homebrew.md).

Run the following command to install Git:
```
brew install git
```

### The manual way
* Download the most recent release from [here](https://sourceforge.net/projects/git-osx-installer/files/latest/download)
* Install GitHub Desktop and launch it
* Click GitHub Desktop in the top left corner of your screen then select `Install Command Line Tool`, this will allow you to use GitHub from command line instead of a GUI.

### Verification
Verify you can connect to GitHub using your SSH Key. If you followed the [Using SSH Keys](using_ssh_keys.md) tutorial you will not need to enter your passphrase.

```
ssh -T git@github.com
```

If you are connecting for the first time, you will get this message, type yes then hit enter to proceed.

```
# The authenticity of host 'github.com (207.97.227.239)' can't be established.
# RSA key fingerprint is xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx.
# Are you sure you want to continue connecting (yes/no)?
```

You may see other things but you should get a line that says something like this:

```
Hi user_name! You've successfully authenticated, but GitHub does not provide shell access.
```

Don't worry about the shell access thing, you don't want that anyway.

### Configuring your Git Profile

```
git config --global user.name "Legal Name"
git config --global user.email "user_name@domain.com"
git config --global core.editor vim
git config --global color.ui auto
```

* Remember to switch vim above to your editor of choice.

## Using Git

### Update Git Repo Fork with Master
This is done from a terminal.

Browse to the cloned repository you want to update and proceed with the following:

* Verify
```
git remote -v
```

* Specify a remote upstream repo to sync with your fork:
```
git remote add upstream <repo_url>
```

* Verify:
```
git remote -v
```

### Update Git Repo Fork with Origin Master

* Fetch branches and commits from the upstream repo. You’ll be storing the commits to master in a local branch upstream/master:
```
git fetch upstream
```

* Checkout your fork’s local master, then merge changes from upstream/master into it.
```
git checkout master
git merge upstream/master
```

* Push your updates up to your fork
```
git push origin master
```

### Updating a feature branch

!!! important
    Do this after you have updated your Git Fork with the Origin Master. (see instructions [above](#update-git-repo-fork-with-origin-master))


* Check out the branch you want to merge into
```
git checkout <feature-branch>
```

* Merge your (now updated) master branch into your feature branch
```
git merge master
```

Depending on your git configuration this may open vim. Enter a commit message, save, and quit vim:

* Press `a` to enter insert mode and append text following the current cursor position.
* Press the `esc` key to enter command mode.
* Type `:wq` to write the file to disk and quit.

* This only updates your local feature branch. To update it on GitHub, push your changes.
```
git push origin <feature-branch>
```

## Cheatsheet for using Git
This is not an exhaustive list of what Git can do, but rather the more common things you may come across in your daily use.

### Create Repositories
_Start a new repository or obtain one from an existing URL_

* Create a new local repository with the specified name
```
git init [project-name]
```
* Download a project and its entire version history
```
git clone [url]
```
### Making changes
_Review edits and craft a commit transaction_

* List all new or modified files to be committed
```
git status
```
* Show file differences not yet staged
```
git diff
```
* Snapshot a file in preparation for versioning
```
git add [file]
```
* Show file differences between staging and the last file version
```
git diff --staged
```
* Unstage a file, but preserve its contents
```
git reset [file]
```
* Record file snapshots permanently in version history
```
git commit -m "[descriptive message]"
```
### Group Changes
_Name a series of commits and combine completed efforts_

* List all local branches in the current repository
```
git branch
```
* Create a new branch
```
git branch [branch-name]
```
* Switch to a specified branch and update a working directory
```
git checkout [branch-name]
```
* Combine a specified branch’s history into the current branch
```
git merge [branch]
```
* Delete a specified branch
```
git branch -d [branch-name]
```
### Refactor Filenames
_Relocate and remove versioned files_

* Delete a file from the working directory and stages the deletion
```
git rm [file]
```
* Remove a file from version control but preserves the file locally
```
git rm --cached [file]
```
* Change a file name and prepares it for commit
```
git mv [file-original] [file-renamed]
```
### Suppress Tracking
_Exclude temporary files and paths_

* A text file named `.gitignore` suppresses accidental versioning of
files and paths matching the specified patterns, examples:
```
*.log
build/
temp-*
```
* List all ignored files in a project
```
git ls-files --other --ignored --exclude-standard
```
### Save Fragments
_Shelve and restore incomplete changes_

* Temporarily store all modified tracked files
```
git stash
```
* Restore the most recently stashed files
```
git stash pop
```
* List all stashed changesets
```
git stash list
```
* Discard the most recently stashed changeset
```
git stash drop
```
### Review History
_Browse and inspect the evolution of project files_

* List version history for the current branch
```
git log
```
* List version history for a file, including renames
```
git log --follow [file]
```
* Show content differences between two branches
```
git diff [first-branch]...[second-branch]
```
* Output metadata and content changes of the specified commit
```
git show [commit]
```
### Redo Commits
_Erase mistakes and craft replacement history_

* Undo all commits after [commit], preserving changes locally
```
git reset [commit]
```
* Discard all history and changes back to the specified commit
```
git reset --hard [commit]
```
### Synchronize Changes
_Register a repository bookmark and exchange version history_

* Download all history from the repository bookmark
```
git fetch [bookmark]
```
* Combine bookmark’s branch into current local branch
```
git merge [bookmark]/[branch]
```
* Upload all local branch commits to GitHub
```
git push [alias] [branch]
```
* Download bookmark history and incorporates changes
```
git pull
```
