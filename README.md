# GitConfigTest

### This is the note for Git in Github
#### push commit: <br>

In the directory that you modified and you want to push<br>
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


