# Git Commands

## Git Flow

Getting started: 

1. Initialise: To start using git-flow inside an existing git repository run `git flow init`. You'll have to answer a few questions regarding the naming conventions for your branches. It's recommended to use the default values.

2. Starting a new feature: To start developing a new feature run `git flow feature start NewFeature`. This action creates a new feature branch based on 'develop' and switches to it.

3. Once a new feature has been created you can then start making changes in the code.
- Run `git add -A` to add all your new changes
- Run `git commit -m "Your commit message"` to commit all the new changes
- Run `git push -u origin feature/FEATURENAME` the first time to push all your new changes, and then `git push` after the first initial push.
- You can then make a pull request to have your new feature merged with the develop branch.

4. Finishing a new feature: Once your new feature has been merge into the develop branch, to finish the development of the feature run `git flow feature finish FEATURENAME`. This action will remove the feature branch and switches back to the develop branch.


## Git Branches

Getting started: 

1. The easiest way is just to use the `git branch` commands’, or various options.
- Run `git branch -a` shows all local and remote branches
- Run `git branch -r` shows only remote branches.
- There’s also another way to do figure out what branches are on your remote by actually using the remote related commands, `git remote` or `git remote show origin` and `git ls-remote` or `git ls-remote --heads origin`.

The `ls-remote` command returns the SHA1 hash of the latest commit for that reference, so it is quite easy to parse out and get to the exact commit you need if you’re doing some scripting. The `--heads` option lists only branch names since the command can list tags too.

2. Once you know the name of the branch it’s quite simple to check them out. Run `git checkout BranchName` i.e git checkout `git checkout develop`.
