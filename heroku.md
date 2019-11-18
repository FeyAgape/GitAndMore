# Deploying to Heroku

If you haven't already log in to your Heroku account

1. run `heroku login`

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

**If pushong to an Existing Git repository**

For existing repositories, simply add the heroku remote

`heroku git:remote -a name-of-the-project`
