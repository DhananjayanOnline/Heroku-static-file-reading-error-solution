# Heroku static file reading error solution

"Error while running '$ python manage.py collectstatic --noinput'" after changing database on django

1. disable the collectstatic during a deploy
heroku config:setDISABLE_COLLECTSTATIC=1
2. deploy
git push heroku master (orgit push heroku <branch>:master ifnoton master)
3. run migrations
heroku run python manage.py migrate
4. run collectstatic using bower
heroku run 'bower install --config.interactive=false;grunt prep;python manage.py collectstatic --noinput'
5. enable collecstatic for future deploys
heroku config:unset DISABLE_COLLECTSTATIC
6. Run collectstatic again
heroku run python manage.py collectstatic

From <https://stackoverflow.com/questions/55330749/error-while-running-python-manage-py-collectstatic-noinput-after-changin> 



$ heroku config:set DISABLE_COLLECTSTATIC=1 | Heroku Error Fixed | 2021


[[image](https://user-images.githubusercontent.com/82816086/219457933-5381aa94-53c0-4510-81c4-77cab85780e5.png)](https://youtu.be/M1L0WKxLn1M)
  
 you can check out the above youtube video for more information
