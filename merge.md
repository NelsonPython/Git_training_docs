
# Merge

Navigate to the ` bugFix ` branch.  View git branch to confirm that HEAD is pointing to ` bugFix `.  Create a new file called ` my_first_merge_md `.

### Checkout bugFix branch

```
$ git checkout bugFix
Previous HEAD position was 8ecbd51 Initial commit
Switched to branch 'bugFix'
 
$ git branch
* bugFix
  main
  newImage
 
$ nano my_first_merge.md
```

### Check out main and merge bugFix

```
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
 
$ git merge bugFix
Already up to date.
```

Main knows about ` bugFix ` but ` bugFix ` does not know about main.  Check out ` bugFix ` and merge main into ` bugFix `.

### Check out bugFix and merge main

```
$ git checkout bugFix
Switched to branch 'bugFix'
 
$ git merge main
Updating 813be9c..c22de5b
Fast-forward
 bugFix1.md  | 1 +
 keepFile.md | 1 +
 saveFile.md | 1 +
 3 files changed, 3 insertions(+)
 create mode 100644 bugFix1.md
 create mode 100644 keepFile.md
 create mode 100644 saveFile.md
```

### Commit merged changes

```
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
 
$ git commit -m 'Merge'
 
On branch bugFix
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        my_first_merge.md
nothing added to commit but untracked files present (use "git add" to track)
 
$ git add my_first_merge.md
 
$ git commit -m 'Merge'
[bugFix c94b3a9] Merge
 1 file changed, 1 insertion(+)
 create mode 100644 my_first_merge.md
 
$ git push
```

