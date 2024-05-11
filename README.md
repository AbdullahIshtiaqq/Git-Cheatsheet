# Git and Github Cheatsheet

**Note:** All commands must be run inside the folder that contains all the code.

## Creating Commits

In git's dictionary, a commit is a version.

**git init :** Git will start tracking all changes in the current folder  
**git status :** Show all changes since the previous commit

**git add <file/folder> :** Pick changes to go into next commit  
&nbsp;&nbsp;&nbsp;&nbsp;**git add file :** Pick individual file  
&nbsp;&nbsp;&nbsp;&nbsp;**git add folder/ :** Pick all files inside a folder (and subfolders)  
&nbsp;&nbsp;&nbsp;&nbsp;**git add . :** Pick all files (in folder command line is running in)

**git commit -m "message" :** Creates a commit with a message attached  
**git commit -m "message" --amend :** Update previous commit instead of creating new one

**git log :** View the commit history  
&nbsp;&nbsp;&nbsp;&nbsp;**git log --all :** Show all commits (not just current branch)  
&nbsp;&nbsp;&nbsp;&nbsp;**git log --all --graph :** Show branching visually in the command line

## Configure Name & Email for Commits

**git config --global user.name "Your Name"**  
**git config --global user.email "email@example.com"**

**Working Area :** contains changes start in the working area  
**Staging Area :** contains changes that will go into the next commit

**working => staging**  
git add .

**staging => commit history**  
git commit -m "message"

**staging => working**  
git reset <file|folder>  
&nbsp;&nbsp;&nbsp;&nbsp;git reset file  
&nbsp;&nbsp;&nbsp;&nbsp;git reset folder/  
&nbsp;&nbsp;&nbsp;&nbsp;git reset .

**working => remove the changes**  
git checkout -- <file|folder>  
&nbsp;&nbsp;&nbsp;&nbsp;git checkout -- file  
&nbsp;&nbsp;&nbsp;&nbsp;git checkout -- folder/  
&nbsp;&nbsp;&nbsp;&nbsp;git checkout -- .

## Viewing previous Commits

**git checkout <commit_hash|branch_name> :** View a previous commit

![Commit History.](/Images/Commit%20History.png)  
master = branch name  
You can git checkout < branch >  
Always points to latest commit on the branch.

HEAD = indicates which commit you are currently viewing

## Restoring to a previous Commit

**git checkout <hash|branch> <file|folder> :** Restore the contents of files back to a
previous commit  
&nbsp;&nbsp;&nbsp;&nbsp;**git checkout <hash|branch> :** file Restore a file  
&nbsp;&nbsp;&nbsp;&nbsp;**git checkout <hash|branch> :** folder/ Restore all files in folder (& subfolders)  
&nbsp;&nbsp;&nbsp;&nbsp;**git checkout <hash|branch> . :** Restore all files in project

## Other Features of Git

**git config --global alias.shortcut <command> :** Creates an alias (a shortcut)  
**git config --global alias.s "status" :** Now, **git s = git status**  
**.gitignore** Tell git which files/folders it SHOULD NOT track

## GitHub

Repository = a folder containing code where any changes to the code are tracked by git.  
(To create a repository, we create a new folder on our computer, and then run **git init**)

GitHub = a service that lets us save our git repositories online. It also helps us:

- backup our code in case we delete it on our computer
- see the history of our code changes more easily
- alternatives include Bitbucket and GitLab

Local repository = a git repository saved on our computer  
Remote repository = a git repository saved online (for example on GitHub)

## Uploading Code to GitHub

**git remote add <remote_name> < url > :** Link a local repository to a remote repository and give a name for this link

**git remote add origin https://github.com/AbdullahIshtiaqq/git-bootcamp**  
^  
The above command links a local repository to a GitHub repository (located at the url
https://github.com/AbdullahIshtiaqq/git-bootcamp) and gives it a name "origin"

**git remote :** List all remote repositories that are linked  
&nbsp;&nbsp;&nbsp;&nbsp;**git remote -v :** List all remote repositories (but with more detail)

**git remote remove <remote_name> :** Removes a link to a remote repository  
&nbsp;&nbsp;&nbsp;&nbsp;**git remote remove origin :** Removes the link to the remote repository named "origin"

**git config --global credential.username <username> :** Configure your GitHub username so you can get access to your Github repository

**git push <remote_name> <branch> :** Upload a branch of your git version history to your remote repository  
&nbsp;&nbsp;&nbsp;&nbsp;**git branch :** Shows a list of available branches  
&nbsp;&nbsp;&nbsp;&nbsp;**git log --all --graph :** Shows the branches visually in the history  
&nbsp;&nbsp;&nbsp;&nbsp;**git push origin main :** Upload the branch "main" to the remote repository named "origin"

**git push <remote_name> <branch> --set-upstream :** Sets up a shortcut for this
branch and remote repository  
&nbsp;&nbsp;&nbsp;&nbsp;**git push origin main --set-upstream :** Next time you are on the main branch and you run git push, it will automatically push the main branch to origin

**git push <remote_name> <branch> -f :** Force-push the branch to the remote repository (it will overwrite what's on the remote repository)

## Downloading code from GitHub

**git clone <url> :** Download a remote repository from a url  
&nbsp;&nbsp;&nbsp;&nbsp;**git clone https://github.com/AbdullahIshtiaqq/git-bootcamp**

**git clone <url> <folder_name> :** Download the repository and give it a different folder name

**git fetch :** Updates all remote tracking branches. Remote tracking branches (like origin/main) show what the branch looks like in the remote repository

**git pull <remote_name> <branch> :** Update the local branch with any updates from
the remote repository (on GitHub)

&nbsp;&nbsp;&nbsp;&nbsp;**git pull origin main :** Downloads any new commits from the main branch on origin, and updates the local main branch with those new commits  
&nbsp;&nbsp;&nbsp;&nbsp;**git pull origin main --set-upstream**  
&nbsp;&nbsp;&nbsp;&nbsp;^  
&nbsp;&nbsp;&nbsp;&nbsp;Sets up a shortcut so that the next time you are on the main branch and run git pull, it will automatically git pull origin main
