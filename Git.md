# Git Commands

## Creating a new repository on the command line

Getting Started: 

1. Optional: You can use echo to create a new file via the command line `echo "# test" >> README.md`

2. Initialise: To start using git inside a new repository that hasn't been initialise with git before, run `git init`

3. Committing your work: once your ready to push it to the repo
- Run `git add -A` this will add all your different file changes.
- Run `git commit -m "commit message here"` this will commit your changes making it ready to be push.
- Run `git remote add origin https://github.com/Usernamme.test.git` this will add in the location of your repo. 
- Run `git push -u origin master` this will send your changes from your local machine to your remote repo, you specify in the step before.

4. Additional pushes: once you've made the first push you dont need to add the remote origin again, so your process will be 
- Run `git add -A` this will add all your different file changes.
- Run `git commit -m "commit message here"` this will commit your changes making it ready to be push. 
- Run `git push` this will send your changes to your remote repo.


