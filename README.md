# GitConfigTest
### This is the test for Git in Github
push commit: <br>
in the directory you modify and you want to push<br>
add file to commit: 	git add .	or 	git add filename<br>
add commit to buffer: 	git commit -m "change name"<br>
First time push:	git remote add origin ssh_repo_address<br>
			git remote set-url origin ssh_repo_address<br>
			git push origin master<br>
push forcely		git push -u origin +master<br>
push to the online: 	git push<br>
pull from the online	git pull<br>

clone command:<br>
git clone git_address<br>

git config:<br>
generate ssh key: ssh-keygen -C 'email_address' -t rsa<br>
	* 'cd .ssh' to get into ssh directory<br>
	* id_rsa is private key<br>
	* id_rsa.pub is public key which is used to connect to github with ssh key<br>

Test connection: ssh -v git@github.com<br>

Initilize git: git init<br>
Then you can create a new repo in github.com<br>

Set user name: git config --global user.name "your user_name"<br>
Set user email: git config --global user.email "your email_addr"<br>

Useful command:<br>
git diff<br>
git status<br>
git branch<br>
git checkout<br>
git stash<br>



