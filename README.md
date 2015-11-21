# DeployHeroku
Heroku部署总结
Download heroku cli application from the web page 

Assume ur rails project folder is myproject

cd to this folder:
cd path_to_this_folder/myproject

Add git:
git init
git add .
git commit -m 'init'

Create heroku application:
heroku create

Upload code:
git push heroku master

Start hosting:
heroku open

Remarks:
1. ssh key added? Use heroku login to check
2. Use PostgreSQL
############################################################################
If you don't want to delete the entire application (perhaps you want to keep your add-ons and other configuration the same), you can reset the database and force update the code.

Deploy your new code, forcing the update by using the -f flag:

git push heroku master -f
Drop and recreate the database:

heroku pg:reset <DATABASE>
Migrate the fresh database:

heroku run rake db:migrate

Destroy the app:
heroku apps:destroy --app exampleCreate a new one:
heroku create examplePush to it:
git push heroku -u master
################################################################################
配置数据库https://devcenter.heroku.com/articles/heroku-postgresql#local-setup
################################################################################
$ rm -rf .git
$ git init

Install the Heroku Toolbelt

Download and install the Heroku Toolbelt or learn more about the Heroku Command Line Interface.

If you haven't already, log in to your Heroku account and follow the prompts to create a new SSH public key.

$ heroku login
Create a new Git repository

Initialize a git repository in a new or existing directory

$ cd my-project/
$ git init
$ heroku git:remote -a augustlong
Deploy your application

Commit your code to the repository and deploy it to Heroku using Git.

$ git add .
$ git commit -am "make it better"
$ git push heroku master

