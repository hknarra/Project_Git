# 1. Working in Master branch:
Clone the git repo to local.
```
$cd git_project   		#move to the project directory  
$git add .			    #add files to staging 
$git commit -m "commit1" 	#add files to repo
$git push  		  	        #Push to repo
```

# 2. Working in a branch:
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


