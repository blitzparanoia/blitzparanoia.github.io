---
layout: post
title:      "Git: A Simple Guide"
date:       2019-03-18 01:23:25 +0000
permalink:  git_a_simple_guide
---

Below are some notes that were taken from a Intro to Git lecture for reference on the procedure and some useful commands. 
This guide is intended to be a quick reference and overview of how to navigate in Git. It is meant to clear up the process and make it less intimidating. Keep in mind the GitHub website allows for the user to use the GUI instead of typing in commands.

***Kindly note that if there are any errors please feel free to reach out.***

### *TL;DR*
In short, the Git and Github procedure is as follows...
1. Fork (create a copy)
2. Clone (copy of repository onto your local machine)
3. Add ( )
4. Commit (with message)
5. Push (upload the changes to the repository back to the remote server)
6. Pull (used to update the local machine copy of the repository with the most up to date changes [important when working in a group and multiple people are making changes to a repository])

#### Let's begin...

`open git`
Takes user to the *repository* of the project
The *repository* is simply where the code lives

**Fork** the project- makes a copy of all the code
Note: The fork is always connected to the parent.

**Clone** the code- this moves the forked copy onto your local machine


`git clone (the url of the forked repository)`

**Terminal Commands to help navigate...**
`ls`  - to look at folder
`cd`  -to change into the folder after searching
`cd ..`  -to go back a folder


#### List of some important Git commands

`git status`
shows where you are at
shows the current state of what you are doing 
displays the branch you are working on and shows if you are up to date.
NOTE: ‘origin/master’ is referring to the remote repository

`git remote -v` 
there is a fetch ( when it was clone) and  push (when changes are made to the server)
remotes are shown for the different actions the file had gone through
NOTE: the git protocol is shown (git) along with the server/ username of user/ name of the repository

Origin refers to the remote and Master refers to the branch

NOTE: There can be multiple remotes 

Bash Tip: `touch <name of file>`
would create a new file

`git add file_name`
would add files

`git add .`
shortcut for git add all  which would add everything that is not staged and not committed 

`git commit`
used when the desired files are ready to be committed / a commit is a moment in time of your code

`git commit -m "Insert message here"`
to commit and add a message, the message (the message could indicate what kind of change/ fix/ modification was made) should be short and concise [less than or equal to 72 characters]

`git commit —amend`
if there is a misspelling or an edit that needs to be made to the  commit message

`git push `
puts the changes made to the repository onto the remote server

***TIP:*** to check to make sure the commit was successful go to the GitHub repository via the website and view the repository, under the commits tab (would show the most recent commits), each commit has a hash key, click on the hash key to see what changed (green= added / red= removed)

**After commits are made and pushed..**
Go to Master repository via GitHub website to start a *PULL REQUEST*
Ensure you are starting at the desired target in this case the master/parent
Propose to *merge* your code to the parent

**Proceed to create the pull request...**
At this point the commit an be reviewed and others may give suggestions on how to improve them. You could makes the necessary changes required

#### What happens if there have been other updates or change on the remote? How do I retrieve the latest version of the repository?

`git status` 
to check if you have the latest version of the repository

`git pull`
would update your local branch, it shows a shorthand description of the files changed. It should update to your local work space automatically.

———
**What is a branch?**
A branch allows you to make changes to code  without disrupting the master 

`git branch`
typing in git branch on your local machine would only show the Master. Showing all the other branches would take up lots of space. 

*To create a new branch*
`git branch <name-of-branch>`
creates a new branch

*To start working on the new branch created, type the following command to switch branch:*
`git checkout <name-of-branch>`

*To delete a branch:*
**ensure you are not on the branch that you want to delete**

`git branch -d <name-of-branch>`
the branch gets deleted form the local machine, it is still up on the remote server

**To delete a branch from the server use the GitHub website**

Suggested easiest way to create a repository is through the GitHub website, the GitHub website also has the instructions on how to set up a new repository via the command line

However, do not be afraid to type in commands because Git would offer help showing possible commands you might be looking for.

Happy Coding!!
