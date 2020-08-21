# h5ai on heroku using git as storage
A modern HTTP web server index for Apache httpd, lighttpd, and nginx.
https://github.com/lrsjng/h5ai
Directly for h5ai is web/ you have to put yor files and folders here

## Deploying
# For heroku(More storage) git 
 deploy using heroku cli add your files under web/ directory and push to heroku 

# For github 
just fork the project and deploy using github on heroku file size linit 100mb

# For gitlab (my prefrence cuz more file size limit) 
for deploying import the repository on your gitlab
then make .gitlab-ci.yml 
```
heroku:
 stage: deploy
 
 script:
 - apt-get update -qy
 - apt-get install -y ruby-dev
 - gem install dpl
 - dpl --provider=heroku --app=$HEROKU_APP_PRODUCTION --api-key=$HEROKU_API_KEY
  
 only:
 - master
```
you will need to setup variables in gitlab ci/cd settings go to settings>CI/CD>Variables
```$HEROKU_APP_PRODUCTION``` Name of your app

```$HEROKU_API_KEY``` heroku api key get it from heroku account settings
