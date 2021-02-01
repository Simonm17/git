# Overview

## Accessing the help function 
git help <verb>  e.g. git help config
or
git <verb> --help   e.g. git config --help
  
## show current git version
git --version

## Setting your global email/name in your computer
git config --global user.name "Ryan Chung"
git config --global user.email "ryanchuung@gmail.com"
## See/check your email/name
git config --list

----------------------------------------------------------------------------------

# Directories/files

### View Folders and Files in the Directory
ls
### Print out folders/files within a directory
ls -la

## Create a file/folder
touch filename
mkdir foldername

## Remove file 
rm filename   #removes file from staging area
rm -r filename  #removes modified file that is already added to staging area
## Remove folder
rmdir foldername  #only works with empty folders
rm -rf foldername  #deletes folders with existing files

## Change directory
cd /c/Users/PC/PycharmProjects/flaskblog
cd .. <-- move back one file e.g. /c/Users/PC/PycharmProjects/
cd ~ <-- move to home directory e.g. /c/Users/PC

## Copy a file
cp existfile newfile   e.g. cp existing_file.py copy_file.py
## Move/rename file
mv existfile newfile

## Open an existing file
explorer filename
explorer .    <-- Open all files and folder in current directory
NOTE: if it doesn't work, try: open filename
### Open with VS Code
code filename
code .

----------------------------------------------------------------------------------

# Adding local files to Github 

## Initiate directory and add files to staging

### Initiate git in root directory
git init
### If you need to remove the .git directory
rm -rf .git

### Add a .gitignore file if you don't want some files added to Github
touch .gitignore
#### List directories or files inside .gitignore
sqlite3  <- refers to files
venv/  <- / refers to directories
.vscode/  <- . refers to extensions
*.log  <- * refers to a catch-all wildcards

### Add files to staging area to be "pushed" to Github
#### Add all the files
git add -A *or* git add .
#### Add specific files/dir
git add fileName
git add dirName/

### Check the status of added/staged directory
git status
#### Red files are not added, green files are added and ready to be committed.

### If you need to reset the staging area, use:
git reset
git reset oneFile.py

----------------------------------------------------------------------------------


## Commit selected files to be "pushed" to Github
### Once you have your files ready, commit them to be "logged" in your local machine.
git commit -m "first commit"
#### When you commit, write a message, commenting what you've done in that commit.
#### If you need to modify your message, you can use:
git commit --amend -m "amended message"

### Viewing commit logs
git log
git log --oneline
git log filename
git log foldername
git log -3  <-- shows the last three commits

### Viewing commits
git show hash
e.g. git show 0da2f7
git show HEAD~1  <-- HEAD~<#> shows log of commit based on the number provided. e.g. HEAD~1 shows previous commit

### viewing detailed commits
git annotate filename

### Checking out a file from an earlier commit
git checkout <commit's number> index.html

### Discard changes that have not yet been staged. Once checked out, discharged changes are gone forever.
git checkout -- filename

### Reset local repo to the end stage commit
1. git reset HEAD index.html
2. git checkout -- index.html
or
git reset --hard

----------------------------------------------------------------------------------

# Pushing local commits to Github

### Go to github.com and create a new repository with default settings.

### Add the remote url so your local machine knows where to push the files to.
git remote add origin <url>

#### url will have a .git in the end

#### Verify remote branch
git remote -v

## First, check for any new commits that may have happened while you were committing yours
git pull origin master
## If no recent outside commits, you can push the changes to Github
git push -u origin master


----------------------------------------------------------------------------------

# Branches

### View remote branches
git remote -v
### View local branches
git branch -a

## Create a new branch
git branch newdir

## Switch to a branch
git checkout newdir
git checkout master

## Create & switch to a new branch
git branch -b newbranch

## Deleting a branch
#### Check merged branches
git branch --merged
#### Delete branch locally
git branch -d drname
#### Check existing branches
git branch -a
#### Delete branch remotely
git push origin --delete drname

## Merging branches
git merge source destination
e.g. git merge subbranch master


