---
layout: post
title:  "Git Commands!"
date:   2018-10-26 13:46:52
comments: true
image: /images/git.jpg
categories: 
---



### Git Configuration steps for NetBackup

	1. git config --global user.name "Vikas Kumar"
	
	2. git config --global user.email vikas.kumar2@xyz.com
	
	3. git config --global push.default simple
	
	4. Windows:	git config --global credential.helper wincred
	Linux:	git config --global credential.helper 'cache --timeout=36000'  


----

### Want to Squash your changes before commit into main or purpose_etrack

#### Unix:
	1. Verify the branch --- git branch
	2. git rebase -i `git merge-base origin/master feature/<branch_name>` feature/<branch_name>
	It means, pull the changes b/w origin and branch and put them into same branch and -i for interactive operation. It will give you a vim console then pick first 
	change and other squash just replacing pick string by squash. You can drop any change by placing drop string in place of pick in that file and save that file. 
	
	or 
	
	git reset --soft `git merge-base origin/master bugfix/serial_no_format_vk`
	
	
	3. Verify the change -- git log
	4. git push --force-with-lease
	
	
----

### Start Working on feature or bug

	1. Create your branch from stash. Branch_Name = "bugfix/XXXX"
	
	2. Clone the netbackup source repository, 
	git clone -n https://Vikas.Kumar2@stash.xyz.com/scm/nb/src.git ./src
	
	3. cd src
	
	4. List out the branch,
	git branch --list --remotes "*bugfix/XXXX*"
	
	5. Checkout your branch, 
	git checkout bugfix/XXXX
	
	6. Make code change.
	
	7. You can check status of your change file.
	git status  --- will give you all files
	git status -uno  -- will skip untracked files.
	git diff
	
	8. Commit your changes to your private branch.
		a. git add <modified files.>
		b. git commit
		c. git push

----

### Want to update your branch with Main/origin branch

#### Method I

    (be in your src directory)
	1. Go to master branch first.    --- git checkout master
	2. Pull all the changes --- git pull
	3. Verify the commit logs ----  git log
	4. Check the branch ----  git branch
	5. Goto your branch -- git checkout bugfix/<branch_name>
	6.  Now ready to merge the master branch and your branch
		git rebase master
	It will merge all the changes. Incase of conflict it will notify you, then resolve the conflicts. In particular file and then 
		git add <resolved_conflict_file> then,
		git rebase -- continue
	7. Verify merge with, ----  git log
	8. Push all the changes to your branch from local to remote
	git push or git push --force-with-lease

----
### Git Stash

	1. git stash -- to put your changes in stack 
	2. git stash apply -- will apply top most stash into your branch.
	3. git stash pop -- will apply and pop the syash from stack  
	4. git stash drop -- will drop the top most stash change
	git stash drop stash@{1}  -- will drop selected satsh
	5.  git stash list -- list out the pushed stashed in stack
	6.  git stash show -p  -- will show the top most stash
	7. git stash show 2694585eed6287bb5e1bc098aff12f4589b86b65
	8. git stash apply 2694585eed6287bb5e1bc098aff12f4589b86b65
	
----

### Some Points on Git

	1. origin means, main branch at remote and master branch means local copy of origin in your branch.
	2. Push change to your branch -- git push --force-with-lease
	3. If you are in your branch, git checkout -- . 
	Will checkout your branch code in your sandbox and override the changes.
	4. git reset cl/nbcertcmd/*  -- will reset whole directory
	5. git fetch origin        # gets you up to date with origin
	git merge origin/master
	or 
	git pull origin master
	6. git gc --prune=now
	7. git format-patch master --stdout > uuid.patch
	8. git apply --check uuid.patch
	9. git apply --stat uuid.patch
	10. git am changes.patch --reject
	11. git remote update 
	12. git config --system http.sslverify false
	13. git branch -d <branch_name>

	14. git checkout tags/NB_8.2_0054 - checkout from perticular tag
	15. git reset --hard origin/master
	
	