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


## Git Rebase

Getting Started

`git rebase` allows you to reapply commits on top of another base tip

1. `git rebase origin/master` 

If there are any conflicts, you will see a message like this



2. run `git status` to see if they're any conflicts by accesses the files 



## Git cherry-pick


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
