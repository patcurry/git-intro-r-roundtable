# Intro to Git
# Pat Curry
# 2017-08-24

## Table of contents
- [What is Git?](#what-is-git)
- [Git is not easy](#git-is-not-easy)
- [Creating a repository](#creating-a-repository)
- [Cloning a repository](#cloning-a-repository)
- [Branching](#branching)
- [Viewing the git log](#viewing-the-git-log)
- [Set a remote repository](#set-a-remote-repository)

- [Resources](#resources)
- [License](#license)

## What is Git
Git is a version control system.
It is a way to track changes in computer files.
Git is also a way for multiple people to work on the same file or files at the same time.

### Git is not easy

Things we will try to cover today
Installing Git
Creating a repository
Making commits
Branching
Navigating commits and branches
Cloning a repository
Pushing commits local and remote repositories

Installing Git

Linux
https://git-scm.com/download/linux

```sh
sudo apt-get install git-all
```

Mac
https://git-scm.com/download/mac

Windows
https://git-scm.com/download/win

Go through the process of installation
On a windows computer be sure that you can use git bash.
It would also be good to open a window to the git repository you are in.
We will have to learn a bit of bash at the same time as learning git.

## Creating a repository
Creating a repository and adding files to it
With Git Bash go to your documents directory then create a new folder initialize a git repository in that folder.

```sh
cd ~/Documents
mkdir learngit
cd learngit
mkdir firstrepo
cd firstrepo
git init
```

Now that you've created the repository let's add a file.
Use pwd to check that you are in the correct directory.
Use git status to check the status of your repository.
Use touch to create a file.

```sh
pwd
git status
touch test.txt
git status
```
Modify test.txt
Open test.txt with a text editor (not microsoft word)
Save test.txt

Check the git status
```sh
 git status
```

Add test.txt to the set of files to be committed

```sh
git add test.txt
```

Check the status again with git status

Make a commit. The "-m" flag is a message that will go along with the commit
```sh
git commit -m 'test.txt has been modified'
```

Check the status again with git status

```sh
 git status
```

## Cloning a repository

Go back into the learngit directory.

```sh
cd ~/Documents/learngit
pwd 
```
You should see this

```sh
/Users/USERNAME/Documents/learngit
```

Now clone the git repository and cd into the repository

```sh
git clone https://github.com/patcurry/rroundtable-git-clone-practice.git 
cd rroundtable-git-clone-practice
```

## Viewing the git log
          
Now you have a local version of the repository.
Let's take a look at the commit log

```sh
git log
```
          
Let make this easier to look at

```sh
git log --oneline --all
```

Graphical
```sh
git log --oneline --all --graph
```
          
More info
```sh
git log --oneline --all --graph --decorate
```
 
Even More info
```sh
git log --all --graph --decorate
```

## Branching
Navigate back to the firstrepo folder
```sh
cd ~/Documents/learngit/firstrepo
git status
```

Check the git branches
```sh
git branch
```
          
Make a new Branch and check it out
```sh
git branch dev
git branch
git checkout dev
```

In the dev branch make a new file and commit the change
```sh
touch superduper.txt 
git status
```

Write something in the file then check the status of the repository and commit the change
```sh
git status
git add .
git status
git commit -m 'added superduper.txt'
```
          
Look at the differences between the dev and the master branches
```sh
git diff master..dev
```

Checkout the master branch and merge the branches
```sh
git checkout master 
ls
git merge dev
git status
```
 
Take a look at the git log
```sh
git log --all --oneline --graph
```
          
## Set a remote repository.
Set up a github or gitlab account or just use the zmt gitlab instance.
https://gitlab.leibniz-zmt.de/users/sign_in
Check out your profile
https://gitlab.leibniz-zmt.de/pcu

Let's set a remote repository.
This can be done with github, gitlab, the zmt gitlab, or bitbucket, and probably more.
Actually, you can set a remote repository on any server, or even your own computer.
```sh
git status
git remote add origin https://gitlab.leibniz-zmt.de/USERNAME/firstrepo.git
```
or

```sh
git status
git remote add origin https://gitlab.com/USERNAME/firstrepo.git
```

or

```sh
git status
git remote add origin https://github.com/USERNAME/firstrepo.git
```
 
          
Set git username and email for your computer
```sh
git config --global user.name "USERNAME"
git config --global user.email "EMAIL"
```

Go to github/gitlab/bitbucket and make the repository!
        
Push initial commit to the remote repository
```sh
git push origin master
```
## Resources

https://git-scm.com/book/en/v2

https://www.atlassian.com/git/tutorials

http://learngitbranching.js.org/

https://try.github.io/levels/1/challenges/1

https://www.codecademy.com/learn/learn-git

## License

MIT licensed

Copyright (C) 2017 Pat Curry
