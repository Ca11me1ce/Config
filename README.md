# GitConfigTest

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
