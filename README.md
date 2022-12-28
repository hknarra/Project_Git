###### #####################################################
# 1. Working in Master branch:
###### #####################################################
Clone the git repo to local.
```
$cd git_project   		#move to the project directory  
$git add .			    #add files to staging 
$git commit -m "commit1" 	#add files to repo
$git push  		  	        #Push to repo
```

###### #####################################################
# 2. Working in a branch:
###### #####################################################
```
$cd git_project   	#move to the project directory  
$git remote set-url origin git@github.com:USERNAME/REPOSITORY.git set remote repo
$git init    		#initializing the current working directory


Branch:
$git branch   			shows list of branches in our local machine
$git branch branch1		create new branch
$git checkout 'branch1'	switches to new branch ‘branch1’
#Work on code or pull from master.

$git add .			add files to staging 
$git commit -m "commit1" 	add files to repo

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
# 3. Merge conflicts:
###### #####################################################
Merge conflicts happen when you merge branches that have competing commits, and Git needs your help to decide which changes to incorporate in the final merge.

Merge conflicts happen:
1.	when people make different changes to the same line of the same file.
2.	when one person edits a file, and another person deletes the same file.

## 3.1. Resolve Merge conflict on same line and same file:
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

## 3.2. Removed file, merge conflicts:
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

## 4.1 Pull all files:
```
$git pull origin master
```

## 4.2 Pull specific file:
```
$git fetch –all
$git checkout origin/master -- README.md   pulling README.md file
```

