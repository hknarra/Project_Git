###### #####################################################
# 1. Git Basics:
###### #####################################################
### 1.1. Basics 
```
which git #gets get location

git --verison #gets version
```

### 1.2 Git Config 
```
System level configuration: 
$git config --system

User level configuration(Changing username, email): 
$git config --global user.name “******”
$git config --global user.email “*****@domain.com”
 
To see configured list?  
$git config --list   		to see the configured file
$git config user.name		to get configured username
$git config user.email		to check configured email 
      

```
### 1.3 Initialize git roject
```
git init
ls -la .git #list files git tracking
```

### 1.4 Git commit log
```
$ git log -n 1				-- gives 1 commit change.
$ git log --since=2016-12-01 --gives commits from the date given
$ git log --until=2016-12-01 --gives up to the date given
$ git log ¬¬--author=”Krishna” --gives particular user log
```

###### #####################################################
# 2. Branch
### 2.1 commit Specific file and check status
###### #####################################################
```
$ git add file.txt 	    adds specific file to staging
$ git commit file.txt 	adds file from staging to repository

$ git status            gives status of files  

$ git commit -m "add git file to project"
```

###### #####################################################
### 2.2 Working in Master branch:
###### #####################################################
Clone the git repo to local.
```
$cd git_project   		#move to the project directory  
$git add .			    #add files to staging 
$git commit -m "commit1" 	#add files to repo
$git push  		  	        #Push to repo
```

###### #####################################################
### 2.3 Working in a branch and change to master and merge branch:
###### #####################################################
```
$cd git_project   	#move to the project directory  
$git remote set-url origin git@github.com:USERNAME/REPOSITORY.git set remote repo
$git init    		#initializing the current working directory


Branch:
$git branch   			shows list of branches in our local machine
$git branch branch1		create new branch
$git checkout 'branch1'	  #switches to new branch ‘branch1’
#Work on code or pull from master.

$git add .			             ==>add files to staging 
$git commit -m "commit1" 	==>add files to repo

Fetch (any other changes by others) from master:
$git fetch --all

Rebase (link b/n branch and master):
$git rebase master


Move to master and merge the branch:
$git checkout master
$git merge branch1


Push the branch:
$git push --set-upstream origin master


Delete the hotfix branch:
$git branch -d branch1
```

###### #####################################################
### 2.3 Working in a branch and creating pull request
###### #####################################################
```
$git pull origin master      #Pull other changes
$git pull origin main_remote_branch #this is main branch in repo
$git checkout 'branch1'      #check out to branch1


--work on the code
$git add.
$git commit -m 'commit-TR-2235_pull_for_'
$git push -u origin <branch_name>

link is generated --check with this link in browser or go to bitbucket and check
-->in git --my work or pull requests
-->you get option as Create pull request (select this)
-->give branch details (destination)
-->give reviewer details done.
-->PR successful (build green)
PR marked ad “needs to work” work on the errors.

```





###### #####################################################
# 3. Merge conflicts:
###### #####################################################
Merge conflicts happen when you merge branches that have competing commits, and Git needs your help to decide which changes to incorporate in the final merge.

Merge conflicts happen:
1.	when people make different changes to the same line of the same file.
2.	when one person edits a file, and another person deletes the same file.

### 3.1. Resolve Merge conflict on same line and same file:
```
In branch_conflcit1:
Edit file main2.py 2nd line
$git add .
$git commit -m ‘commit from your branch’

In master:
Edit file main2.py 2nd line
$git add .
$git commit -m ‘commit from master’

$git merge branch_conflict1
====Merge conflict error====


In your branch or master branch your working, do as below:
Remove lines:
<<<<<<< HEAD (current change)
=======
>>>>>>> branch_conflict1 (incoming change)

$git add main2.py
$git commit -m ‘commit after resolving merge conflict’
$git push
```

### 3.2. Removed file, merge conflicts:
```
$git checkout branch1	2nd user branch
$git rm main2.py		file deleted
$git add .
$git commit -m ‘commit for merge conflict’

$git checkout master   	your branch
#Edit file & add code. 
$git add .
$git commit -m ‘commit from master’
$git merge branch1
CONFLICT (modify/delete): main2.py deleted in branch1 and modified in HEAD. Version HEAD of main2.py left in tree.
Automatic merge failed; fix conflicts and then commit the result.

Add the file or remove the file. 
$ git add main2.py
$git merge branch1
$ git push --set-upstream origin master
```
###### #####################################################
# 4. Git Pull
###### #####################################################
Pull remote branch to your branch
```
$git branch branch1
$git checkout branch1
```

### 4.1 Pull all files:
```
$git pull origin master
```

### 4.2 Pull specific file:
```
$git fetch –all
$git checkout origin/master -- README.md   pulling README.md file
```

###### #####################################################
# 5. Reset Last commit
###### #####################################################
```
$git reset HEAD~		to undo files added, commited

Remote mail from bit bucket doesn’t match with local mail id.
$git commit --amend --author=”git_name <git_mail>”
```



