## How to deploy with Heroku
vs code > terminal > Git Bash
```
$ heroku login
```
create heroku app (you can also do this at heroku.com)
```
$ heroku create <heroku_app_name>
```
create **Procfile** 
> web: gunicorn app:app \
> *#web: gunicorn app:<python file name w/o .py>, gunicorn must be installed in advance*

create **runtime.txt** 
> python-3.10.0 \
> *#google a python version for heroku*

create requirements.txt file automatically
```
$ pip freeze > requirements.txt 
```
git add all to staging area and commit
```
$ git add . && git commit -m 'initial deploy'
```
now everything is in the local repository \
we need to add our remote repository in order to push that to heroku
```
$ heroku git:remote -a <heroku_app_name>
$ git push heroku master 
```
if the push gives an error, try below
```
$ git push heroku HEAD:master
```
