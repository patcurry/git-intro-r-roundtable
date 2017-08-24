# Intro to Git
# Pat Curry
# 2017-08-24

## Table of contents
- [What is Git?](#what-is-git)
- [Git is not easy](#git-is-not-easy)

- [Configuration](#configuration)
- [Presentation Size](#presentation-size)
- [Dependencies](#dependencies)
- [Ready Event](#ready-event)
- [Auto-sliding](#auto-sliding)
- [Keyboard Bindings](#keyboard-bindings)
- [Touch Navigation](#touch-navigation)
- [Lazy Loading](#lazy-loading)
- [API](#api)



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

                cd ~/Documents/learngit
                pwd 
              </code>
            </pre>
            You should see this
            <pre>
              <code>
                /Users/USERNAME/Documents/learngit
              </code>
            </pre>
          </section>

          <section>
            Now clone the git repository and cd into the repository
            <pre>
              <code>
                git clone https://github.com/patcurry/rroundtable-git-clone-practice.git 
                cd rroundtable-git-clone-practice
              </code>
            </pre>
          </section>

## Viewing the git log
          <section>
            Now you have a local version of the repository.
            Let's take a look at the commit log
            <pre>
              <code>
                git log
              </code>
            </pre>
          </section>

          <section>
            Let make this easier to look at
            <pre>
              <code>
                git log --oneline --all
              </code>
            </pre>
          </section>

          <section>
            Graphical
            <pre>
              <code>
                git log --oneline --all --graph
              </code>
            </pre>
          </section>

          <section>
            More info
            <pre>
              <code>
                git log --oneline --all --graph --decorate
              </code>
            </pre>
          </section>

          <section>
            Even More info
            <pre>
              <code>
                git log --all --graph --decorate
              </code>
            </pre>
          </section>
        </section>

      <!-- Slide 7 -->



      <!-- Slide 8 -->
        <section>
          <section>
            Branching
          </section>

          <section>
            Navigate back to the firstrepo folder
            <pre>
              <code>
                cd ~/Documents/learngit/firstrepo
                git status
              </code>
            </pre>
          </section>

          <section>
            Check the git branches
            <pre>
              <code>
                git branch
              </code>
            </pre>
          </section>

          <section>
            Make a new Branch and check it out
            <pre>
              <code>
                git branch dev
                git branch
                git checkout dev
              </code>
            </pre>
          </section>

          <section>
            In the dev branch make a new file and commit the change
            <pre>
              <code>
                touch superduper.txt 
                git status
              </code>
            </pre>

            Write something in the file then check the status of the repository and commit the change
            <pre>
              <code>
                git status
                git add .
                git status
                git commit -m 'added superduper.txt'
              </code>
            </pre>
          </section>

          <section>
            Look at the differences between the dev and the master branches
            <pre>
              <code>
                git diff master..dev
              </code>
            </pre>
          </section>

          <section>
            Checkout the master branch and merge the branches
            <pre>
              <code>
                git checkout master 
                ls
                git merge dev
                git status
              </code>
            </pre>
          </section>

          <section>
            Take a look at the git log
            <pre>
              <code>
                git log --all --oneline --graph
              </code>
            </pre>
          </section>

        </section>

<!-- This section needs to be moved to the bottom -->

        <section>
          <section>
            Let's set a remote repository.
          </section>

          <section>
            Set up a github or gitlab account or just use the zmt gitlab instance.
            https://gitlab.leibniz-zmt.de/users/sign_in
            Check out your profile
            https://gitlab.leibniz-zmt.de/pcu

          </section>

          <section>
            Let's set a remote repository.
            This can be done with github, gitlab, the zmt gitlab, or bitbucket, and probably more.
            Actually, you can set a remote repository on any server, or even your own computer.
            <pre>
              <code>
                git status
                git remote add origin https://gitlab.leibniz-zmt.de/USERNAME/firstrepo.git
              </code>
            </pre>
          </section>

        <section>
          Set git username and email for your computer
          <pre>
            <code>
              git config --global user.name "USERNAME"
              git config --global user.email "EMAIL"
            </code>
          </pre>
        </section>

          <section>
            Push initial commit to the remote repository
            <pre>
              <code>
                git push origin master
              </code>
            </pre>
            <span class="fragment fade-in">
              <p class="fragment highlight-red">It didn't work!!!!
            </span>
          </section>

          <section>
            Go to github/gitlab/bitbucket and make the repository
          </section>

          <section>
            Now push to the remote.
          </section>

          <section>
            That's all I'm going to teach you today.
          </section>

        </section>

      <!-- Slide 9 -->
        <section>
          Resources
          https://git-scm.com/book/en/v2
          https://www.atlassian.com/git/tutorials
          http://learngitbranching.js.org/
          https://try.github.io/levels/1/challenges/1
          https://www.codecademy.com/learn/learn-git
        </section>





## License

MIT licensed

Copyright (C) 2017 Pat Curry
