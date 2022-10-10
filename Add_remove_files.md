# Adding and removing files

Git may find files on your local machine that have not been checked in.  Git identifies these as untracked files.  When you check in a file, Git begins tracking it.  Tracked files can be unmodified, modified, or staged.  The first time you check in a file, the git status will change to tracked / unmodified.  As you edit the file, the status changes to tracked / modified.  When files are ready to be committed, they are staged.  See how this works by navigating to the main branch.  Use git status to double check that you are on the main branch.

### Check the status

```
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean
 
$ git push
Username for 'https://github.com': UserName
Password for 'https://UserName@github.com':
Everything up-to-date
$ git status
 
$ On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

Create a new file called ` bugFix1.md `   Commit this new file. 


### Create a new file

```
$ nano bugFix1.md
 
$ git commit -a -m 'Fix bug 1'
 
On branch main
Your branch is up to date with 'origin/main'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        bugFix1.md
nothing added to commit but untracked files present (use "git add" to track)
```

` bugFix1.md ` is listed under the “Untracked files” heading in your status output.   Untracked indicates that Git found a file that was not in the previous snapshot (commit) and this file has not been staged.  Add ` bugFix1.md ` and commit it.

### Add the new file

```
$ git add bugFix1.md
 
$ git commit -a -m 'Fix bug 1'  
 
[main f4d3ecd] Fix bug 1
 1 file changed, 1 insertion(+)
 create mode 100644 bugFix1.md
```

Git staging allows you to select and ignore specific files.  If you want to skip staging and commit all the new files, use git commit -a 

## Removing files

For purposes of example, use your favorite text editor to create another new file called ` newFile.md `


### Check the status

```
$ nano newFile.md
 
$  git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
 
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        newFile.md
nothing added to commit but untracked files present (use "git add" to track)
```


` newFile.md ` is not tracked until it is added to git.  Add ` newFile.md `.  

### Add file and check status

```
$ git add newFile.md
 
$  git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
 
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   newFile.md
```

Git is now tracking newFile.md.  Suppose you realize that you must delete newFile.md.  Remove newFile.md from your local machine.  When you Git status, Git knows that you deleted the file and offers suggestions.  newFile.md appears under both of these sections:  Changes to be committed and Changes not staged for commit.

### Check status

```
$ rm newFile.md
 
$  git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
 
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   newFile.md
 
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    newFile.md
```

Remove the file from git and check the status again to see a clean working tree

### Remove a file from git

```
$  git rm newFile.md
rm 'newFile.md'
 
$  git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working tree clean
 
$ git push
Username for 'https://github.com': UserName
Password for 'https://UserName@github.com':
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 336 bytes | 24.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/NelsonPython/Git_Training
   813be9c..f4d3ecd  main -> main
```
