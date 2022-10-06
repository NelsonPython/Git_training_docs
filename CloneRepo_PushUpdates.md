# Hello Git Clone World

Get started by cloning a Github repo, adding content, and pushing updates back to Github.

## Prerequisites: 

1. Set up a repo using your Github account.  Make sure to include a README.md file
2. Create a PAT (personal access token)
3. This example was tested using Ubuntu 20.04 LTS installed on Microsoft Windows Subsystem for Linux (WSL) on Windows 10.

## Github repo

![](images/Git_beg.png)


## Configure git on local machine

If git config has not been set up, set your username, email address, and text editor.  View the git config file to verify your updates.

```
$ git config --global user.name UserName
$ git config --global user.email UserName@email.com
$ git config --global core.editor nano$ git config --list
user.name=UserName
user.email=UserName@email.com
core.editor=nano
```
For more information see:  https://linuxhint.com/install-use-git-linux/

## Clone the repo

Cloning downloads a copy of everything in the repo

```
$ git clone https://github.com/UserName/Git_Training

Cloning into 'Git_Training'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 6 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 1.22 KiB | 2.00 KiB/s, done.
```

## Navigate to the repo folder

Using command line instructions, navigate to the repo

``` 
$ cd Git_Training
```

View the git log to view the commits.  If you created a repo from scratch, then your log may look similar to this example: 

```
$ git log
```

![Git log](images/log.png)

The first commit is the initial commit when the repo was created.  The second is an update to add the README.md.  More details about the git log will be covered later.  Check the status to find which branch you are on.    Type q to quit viewing the git log.

```
$ git status

On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

## Create a new branch

Suppose you are fixing a bug.  Create a new branch called bugFix.

```
$ git checkout -b bugFix

Switched to a new branch 'bugFix'
```

When you created the branch, git moved you to the new branch.

```
$ nano bugBountyHunters.md
$ git commit -a -m 'Create a new file'

On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        bugFix.md

nothing added to commit but untracked files present (use "git add" to track)
```

Git offers suggestions to guide you.  In this example, bugBountyHunters.md has not been staged and appears under the “Untracked files” section.   Untracked indicates that Git found a file that was not in the previous snapshot (commit) and this file has not been staged.  Follow the suggestion to add bugBountyHunters.md using "git add".  Git stages the file so you can commit it.

```
$ git add bugBountyHunters.md

$ git commit -a -m 'Create a new file'

[bugFix fd209ac] Create a new file
 1 file changed, 3 insertions(+)
 create mode 100644 bugBountyHunters.md
```

Now, your update is ready to be merged into the main branch of code.  First, switch to the main branch.

```
  $ git checkout main

Switched to branch 'main'
Your branch is up to date with 'origin/main'.
```

In the screen capture below, notice the green boxes showing that bugBountyHunters.md file appears in the bugFix branch and in your local folder.    Look at the blue boxes.  When you switch to the main branch and list files, it does not appear.  

![](images/bugFix-main.png)


## Merge

Merge the bugFix branch into the main branch.

```  
$ git merge bugFix
  
Updating 3df6c62..fd209ac
Fast-forward
 bugBountyHunters.md | 3 +++
 1 file changed, 3 insertions(+)
 create mode 100644 bugBountyHunters.md
```

## Push the changes back to Github.

  Use your PAT (personal access token) instead of your Github password.

```
$ git remote add bugFix https://github.com/UserName/Git_Training

$ git push -f bugFix main

Username for 'https://github.com': UserName
Password for 'https://UserName@github.com':
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 366 bytes | 6.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/UserName/Git_Training
   3df6c62..fd209ac  main -> main```
```

bigBountyHunters.md now appears in your Github repo

![](images/Git_end.png)


