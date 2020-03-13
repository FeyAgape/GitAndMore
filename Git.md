# Git Commands

## Creating a new repository on the command line

Getting Started: 

1. Optional: You can use echo to create a new file via the command line `echo "# test" >> README.md`


2. Initialising git: To start using git inside a new repository that hasn't been initialise with git before, run `git init`

3. Committing your work: once your ready to push it to the repo
- Run `git status` displays the state of the working directory and the staging area. It lets you see which changes have been staged, which haven't, and which files aren't being tracked by Git.
- Run `git commit filename.ext` to commit each individual file or`git add -A` this will add all your different file changes.
- Run `git commit -m "commit message here"` this will commit your changes making it ready to be push.
- Run `git remote add origin https://github.com/Usernamme.test.git` this will add in the location of your repo. 
- Run `git push -u origin master` this will send your changes from your local machine to your remote repo, you specify in the step before.

4. Additional pushes: once you've made the first push you don't need to add the remote origin again, so your process will be 
- Run `git commit filename.ext` or `git add -A` this will add all your different file changes.
- Run `git commit -m "commit message here"` this will commit your changes making it ready to be push. 
- Run `git push` this will send your changes to your remote repo.

###### Extra

- run `git show` - for a single commit will shows the log message and textual difference
- run `git show --stat` - will show you the changes made
- run `git log --stat` - will show you the commits message and files changes made
- run `git log` - will show you the commits message
- run `git reset --soft HEAD~1` - this will undo your last commit
- run `git commit --amend --signoff` this will help signoff the previous commit and then `git push --force-with-lease origin master` or `git push --force-with-lease` to update master

## Creating a new repository on the command line

1. Run `git add -A`
2. Run `git commit -m "commit message here"` this will commit your changes making it ready to be push. 
3. Run `git push` this will send your changes to your remote repo.

## Git Flow

Getting started: 

1. Initialise: To start using git-flow inside an existing git repository run `git flow init` or  `git flow init -fd`. You'll have to answer a few questions regarding the naming conventions for your branches. It's recommended to use the default values.

2. Starting a new feature: To start developing a new feature run `git flow feature start NewFeature`. This action creates a new feature branch based on 'develop' and switches to it.

3. Once a new feature has been created you can then start making changes in the code.
- Run `git add -A` to add all your new changes
- Run `git commit -m "Your commit message"` to commit all the new changes
- Run `git push -u origin feature/FEATURENAME` the first time to push all your new changes, and then `git push` after the first initial push.
- You can then make a pull request to have your new feature merged with the develop branch.

4. Finishing a new feature: Once your new feature has been merge into the develop branch, to finish the development of the feature run `git flow feature finish FEATURENAME`. This action will remove the feature branch and switches back to the develop branch.

5. For help run `git flow help` and you should recieve the following instruction.
```
usage: git flow <subcommand> Available subcommands are:
  
   init      Initialize a new git repo with support for the branching model.
  usage: git flow init [-h] [-d] [-f] - Setup a git repository for git flow usage. Can also be used to start a git repository.

    -h, --help            Show this help
    --showcommands        Show git commands while executing them
    -d, --[no]defaults    Use default branch naming conventions
    -f, --[no]force       Force setting of gitflow branches, even if already configured
    --Use                 config file location
    --local               use repository config file
    --global              use global config file
    --system              use system config file
    --file ...            use given config file
    
   feature   Manage your feature branches.
   bugfix    Manage your bugfix branches.
   release   Manage your release branches.
   hotfix    Manage your hotfix branches.
   support   Manage your support branches.
   version   Shows version information.
   config    Manage your git-flow configuration.
   log       Show log deviating from base branch.

Try 'git flow <subcommand> help' for help or git flow init --help.
```


## Git Branches

Getting started: 

1. The easiest way is just to use the `git branch` commands’, or various options.

- Run `git fetch` "downloads" any new changes from the remote to your local repository, `git fetch --all` will fetch all remotes.
- Run `git branch -a` shows all local and remote branches
- Run `git branch -r` shows only remote branches.
- There’s also another way to figure out what branches are on your remote by actually using the remote related commands, `git remote` or `git remote show origin` and `git ls-remote` or `git ls-remote --heads origin`.

The `ls-remote` command returns the SHA1 hash of the latest commit for that reference, so it is quite easy to parse out and get to the exact commit you need if you’re doing some scripting. The `--heads` option lists only branch names since the command can list tags too.

2. Once you know the name of the branch it’s quite simple to check them out. 
- Run `git checkout BranchName` i.e git checkout `git checkout develop`.
- If it's a feature branch: Run `git checkout feature/featurename` i.e git checkout `git checkout feature/task1`.

3. Creating a new branch
- Run `git checkout -b branchname`
- Run `git branch` to check that it has actually created the branch for you`

4. Deleting a branch 
- Run `git branch -d branchname`


## Git Rebase

Getting Started

`git rebase` allows you to reapply commits on top of another base tip

1. run `git fetch` to "downloads" any new changes from the remote to your local repo

2. run `git rebase origin/master` 

If there are any conflicts, you will see a message similar to the below.

![alt text](https://github.com/FeyAgape/GitAndMore/raw/master/image1.png "Image1")



Step A - run `git status` to see where or which files contains conflicts.

Step B - Access the files and resolved the conflicts and then run `git add filename.ext`

- run `git status` and repeat Step A + B untill all conflicts are resolved.

2. run `git rebase --continue`

3. run `git push --force-with-lease`

More [info](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)


## Rebasing your local Branch (to clean up your commits)

Getting Started: First find out how many commit their are first

1. run `git rebase -i HEAD~9`

Breaking this command down:
- `git rebase` — tells our terminal we are running Git with the rebase command
- `-i` — tells git rebase to run in interactive mode (VIM)
- `HEAD~9` — because we want the ability to rebase the last 9 commits (we don’t want to change our initial commit message), the number will depend on the number of commits in your local branch.

2. You will get an option in the Vim editor commands of 

```
p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
```

3. choose your option but for tidying up your commits, i will recommend squashing all commits into 1 and (pick or reword), but choose accordning to need.

4. Save all the changes that you did in the vim editor by running `:wq` to save and exit the vim editor.

5. Run `git log` to see everything that we expected did indeed happen.


## Vim Editor Basics 

**Insert Mode**: The Insert mode lets you insert text in a document. The shortcut is: `i` (insert text where the cursor is) or `o` (insert text at the beginning of the following line).

**Visual Mode**: The visual mode permits the user to select the text as you would do with a mouse but using the keyboard instead of the mouse. Useful to copy several lines of text for example. The shortcut is: `V`.

**Command Mode**: When you are in another mod you can use the escape key (sometimes you'll need to hit it twice) to come back to command mod at any time. A command begins with the symbol `:`.

**Editing**

- In command mode. To start editing the file content, enter: `:i[enter]`

- When you are finished with editing, press the [esc] key to go back to the command mode.

- To save the file and exit the editor, enter: `:x[enter]`

- In case you want to quit vim without saving the file, enter: `:q![enter]`


**Extra's**: Vim Command Reference

```
save: :w
save and exit: :wq
exit: :q
force: ! (example :w! :q!)
vertical split: open a document and then type :vsplit /path-to-document/document and this will open the specified document and split the screen so you can see both documents.
copy: y
copy a line: yy
paste: p
cut: d
cut a line: dd
```

More information [here](https://www.howtoforge.com/vim-basics)


## Git cherry-pick

Cherry picking is the act of picking a commit from a branch and applying it to another. git cherry-pick can be useful for undoing changes.


## Git Merge - Check out, review, and merge locally

1. Fetch and check out the branch for this merge request

```
git fetch origin
git checkout -b branchname origin/branchname
```

2. Review the changes locally

3. Merge the branch and fix any conflicts that come up

```
git fetch origin
git checkout origin/develop
git merge --no-ff branchname
```

Step 4. Push the result of the merge to the repository

`git push origin develop`

