# GitConfigTest
#This is the test for Git in Github
push commit: <b>
in the directory you modify and you want to push<b>
add file to commit: 	git add .	or 	git add filename<b>
add commit to buffer: 	git commit -m "change name"<b>
First time push:	git remote add origin ssh_repo_address<b>
			git remote set-url origin ssh_repo_address<b>
			git push origin master<b>
push forcely		git push -u origin +master<b>
push to the online: 	git push<b>
pull from the online	git pull<b>

clone command:<b>
git clone git_address<b>

git config:<b>
generate ssh key: ssh-keygen -C 'email_address' -t rsa<b>
	* 'cd .ssh' to get into ssh directory<b>
	* id_rsa is private key<b>
	* id_rsa.pub is public key which is used to connect to github with ssh key<b>

Test connection: ssh -v git@github.com<b>

Initilize git: git init<b>
Then you can create a new repo in github.com<b>

Set user name: git config --global user.name "your user_name"<b>
Set user email: git config --global user.email "your email_addr"<b>

Useful command:<b>
git diff<b>
git status<b>
git branch<b>
git checkout<b>
git stash<b>



