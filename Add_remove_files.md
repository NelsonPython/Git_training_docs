# Adding and Removing Files

Git may find files on your local machine that have not been checked in.  Git identifies these as untracked files.  When you check in a file, Git begins tracking it.  Tracked files can be unmodified, modified, or staged.  The first time you check in a file, the git status will change to tracked / unmodified.  As you edit the file, the status changes to tracked / modified.  When files are ready to be committed, they are staged.  See how this works by navigating to the main branch.  Use git status to double check that you are on the main branch.

### Check the status

```
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

` bugFix1.md ` is listed under the "Untracked files" heading in your status output.   Untracked indicates that Git found a file that was not in the previous snapshot (commit) and this file has not been staged.  Add ` bugFix1.md ` and commit it.

### Add the new file

```
$ git add bugFix1.md
 
$ git commit -a -m 'Fix bug 1'
 
[bugFix1 fd209ac] Create a new file
 1 file changed, 3 insertions(+)
 create mode 100644 bugFix1.md
 ```

Git staging allows you to select and ignore specific files.  If you want to skip staging and commit all the new files, use ` git commit -a `


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

Git is now tracking newFile.md.  Suppose you realize that you must delete ` newFile.md `.  Remove ` newFile.md ` from your local machine.  When you Git status, Git knows that you deleted the file and offers suggestions.  newFile.md appears under both of these sections:  Changes to be committed and Changes not staged for commit.



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
```
