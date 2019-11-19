# Deploying to Heroku

If you haven't already log in to your Heroku account

1. run `heroku login` in the terminal and follow instructions

2. Create a new Git repository
Initialize a git repository in a new or existing directory

```
cd my-project/
git init
heroku git:remote -a name-of-the-project
```

3. Deploy your application

Commit your code to the repository and deploy it to Heroku using Git.
```
git add .
git commit -am "make first commit"
git push heroku master
```

**If pushing to an Existing Git repository or from a branch**

For existing repositories, simply add the heroku remote

`heroku git:remote -a name-of-the-project-or-app`


If you are pushing from a branch - not master - 

run `git push heroku <branch_name>:master`


4. Set a Username and Password for the prototype

```
heroku config:set USERNAME=username_here
heroku config:set PASSWORD=password_here
```



