# Deploying to Heroku

## Log in to heroku via your terminal

If you haven't already log in to your Heroku account

1. run `heroku login` in the terminal and follow instructions



## Create a new Git repository if it's a new project

Initialize a git repository in a new or existing directory

Run

```
cd my-project/
git init
heroku git:remote -a name-of-the-project
```

## If pushing to an existing Git repository

Simply add the heroku remote

Run

`heroku git:remote -a name-of-the-project-or-app`



## Deploy your application

Commit your code to the repository and deploy it to Heroku using Git.

Run

```
git add .
git commit -am "make first commit"
git push heroku master
```

## Deploying from a branch

If you are pushing from a branch - not master 

Run

```
git add .
git commit -am "make first commit"
git push heroku <branch_name>:master
```

## Optional: Set a Username and Password for the app

Run

```
heroku config:set USERNAME=username_here
heroku config:set PASSWORD=password_here
```



