# Config

## GIT
## HEROKU
## MYSQL

-----------------------------------------------------------------
### This is the note for the Git to connect to the Github
### Process:
0. Download Git<br>

1. In dir '~', initialize git <br>
```bash
git init
```

2. Construct a new folder as Git Work Station in '~'<br>

3. Construct ssh key<br>
```bash
ssh-keygen -t rsa -C "your_email@email.com"
```
> Always press 'ENTER', ignore password setting.<br>

4. The ssh key is in '~'<br>
```bash
cat ~/.ssh/id_rsa.pub
```
> Copy ssh public key, and go to https://www.github.com<br>
> Go to Profile>>Setting>>SSH and GPG keys, create a new ssh key and paste ssh public key.<br>

5. Test connection
```bash
ssh -T git@github.com
```

6. Set Username and email
```bash
git config --global user.name "your name"
git config --global user.email "your_email@email.com"
git config --list
```
7. Download your necessary repo.<br>

8. In the repo, use git_push.sh to commit modifications.<br>
------
#### Push Commit: <br>
<b>git_push.sh</b><br>
```bash
git add .
git commit -m "Updates"
git push
```

<b>In the directory that you modified and you want to push</b><br>
Add file to commit: <br>	
> git add . <br>
	
or 	<br>

> 	git add filename 

Add commit to buffer: 	<br>

> 	git commit -m "change name"

First time push:<br>	

> 	git remote add origin ssh_repo_address <br>
> 	git remote set-url origin ssh_repo_address <br>
> 	git push origin master <br>

push forcely:	<br>	

> 	git push -u origin +master

push to the online: 	<br>

> 	git push

pull from the online:	<br>

> 	git pull
------
#### clone command:<br>
> git clone git_address<br>
------
#### git config:<br>
generate ssh key: 
>	ssh-keygen -C 'email_address' -t rsa<br>
* 'cd .ssh' is used to get into ssh directory<br>
* id_rsa is private key<br>
* id_rsa.pub is public key which is used to connect to github with ssh key<br>
------
#### Test connection: 
> ssh -v git@github.com<br>
------
#### Initialize git: 
> git init<br>
------
#### Then you can create a new repo in github.com<br>
------
#### Set user name: 
> git config --global user.name "your user_name"<br>
#### Set user email: 
> git config --global user.email "your email_addr"<br>
------
#### Useful commands:<br>
* git diff<br>
* git status<br>
* git branch<br>
* git checkout<br>
* git stash<br>

#### Revert Commit
1. Already git push
```bash
git check "tag"	# Must set tag, which means a version name
```

2. Rollback in corresponding file
```bash
git log "file_name"
git  check "commit_id" "file_name"

# Rollback to commit_id in the file
git commit -am "rollback note"
# That will have a commit log, and does not delete previous commit - Will keep all logs
# Record even the record is rollback
git push origin master
```

3. Revert and delete the log
```bash
# delete newest commit - has the log
git revert HEAD	# HEAD is the newest commit
git push origin master	# It will have a record in log
```

3.1 The best revert method, revert everything materials and remove all logs, but DANGEROUS***
```bash
# delete newest commit - remove logs
git reset --hard HEAD^	# HEAD is the newest commit
git push origin master -f
# It does not have a commit log and it remove the newest log
```

4. Rollback to a corresponding commit
```bash
git log
git revert "commit_id"
```


### Create a branch

```
git check -b branch_name
git push -u origin branch_name

or

Create a branch in Bitbucket/Github online
```



### View branch

```
Git branch
Git branch -a
```



### Update remote git repository in local git copy

```bash
git fetch
```



### Switch branch

```
git checkout branch_name
git checkout master
git checkout version_4
```



### Rename/delete branch

```
git branch -m old new
git branch --move old new
git branch --delete branch_name
```



### Push to branch

```
git add .
git commit -am "commit_name"
git push origin branch_name
```



### Merge to master

```
git add .
git commit -am "commit_name"
git push origin branch_name

git checkout master
// git pull origin master # If multiple developer work in one project, pull first
git merge brance_name
// git status
git push origin master
```



### Done


# Heroku Deployment
1. Heroku register: https://heroku.com
2. Download Heroku CLI: https://devcenter.heroku.com/articles/heroku-cli
3. Start Heroku toolkit run: 
```bash
heroku login
```
4. Install Git
5. $git init -> in the project folder
```bash
git init
git add .
git commit -am "updates"
```
6. Create Heroku app
```bash
heroku create <app_name> # create app
heroku app # show the app
```
7. Config database
```bash
heroku addons:create heroku-postgresql:hobby-dev # create database, will get a DATABASE_URL
heroku pg:promote DATABASE_URL # promote the database
```
8. Create Procfile <- Heroku running file
```
web: gunicorn app:app 
# this first app is app.py - your start file or the project
# the second app is the object app in app.py
```
9. Create requirements.txt, run command
```bash
 pip freeze > requirements. txt
 # Must contain gunicorn==18.0
```
10. Deploy to Heroku, run command: 
```bash
git push heroku master
```

### Some useful commands: 
```bash
heroku run python # run python in heroku platform
heroku restart
heroku app:destroy <app_name> # delete app
```
https://blog.csdn.net/jiulixiang_88/article/details/80604389


## MySQL in Ubuntu
```bash
sudo apt install mysql-client-core-8.0
sudo apt-get install mysql-server
sudo mysql -uroot -p	# login MySQL
systemctl status mysql.service
```
