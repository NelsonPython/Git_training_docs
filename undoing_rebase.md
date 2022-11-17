# Undoing a rebase or a merge

Continue using your local repo and your personal Github account.  This is the most popular method discussed on [Stack Overflow for undoing a git rebase](https://stackoverflow.com/questions/134882/undoing-a-git-rebase).  Use git reflog to find the head commit of the branch immediately before you rebased.  In our example, HEAD@{3} is the head commit before the newFeature was added.


```
$ git reflog
 
7abe6e6 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: commit: Add my new feature
61d5038 (newFeature) HEAD@{1}: checkout: moving from newFeature to main
61d5038 (newFeature) HEAD@{2}: checkout: moving from main to newFeature
 
61d5038 (newFeature) HEAD@{3}: commit: Merge
 
dc68391 (newImage, bugFix) HEAD@{4}: checkout: moving from bugFix to main
dc68391 (newImage, bugFix) HEAD@{5}: merge main: Fast-forward
654dccf (bugFix/main) HEAD@{6}: checkout: moving from main to bugFix
dc68391 (newImage, bugFix) HEAD@{7}: checkout: moving from bugFix to main
654dccf (bugFix/main) HEAD@{8}: checkout: moving from 40b9bc9da0287af7f9abdd50ef550834973af577 to bugFix
40b9bc9 HEAD@{9}: checkout: moving from e24ff9a21f1bc94d7f94ed0dbf9e119dbca60caa to HEAD~3
e24ff9a HEAD@{10}: checkout: moving from main to HEAD^
dc68391 (newImage, bugFix) HEAD@{11}: checkout: moving from e24ff9a21f1bc94d7f94ed0dbf9e119dbca60caa to main
e24ff9a HEAD@{12}: checkout: moving from newImage to main^
dc68391 (newImage, bugFix) HEAD@{13}: checkout: moving from main to newImage
dc68391 (newImage, bugFix) HEAD@{14}: commit (amend): Attempt to add two new files
57cfb94 HEAD@{15}: commit: Attempt to add two new files
e24ff9a HEAD@{16}: commit: Fix bug 1
654dccf (bugFix/main) HEAD@{17}: merge bugFix: Fast-forward
5a7ef02 HEAD@{18}: checkout: moving from bugFix to main
654dccf (bugFix/main) HEAD@{19}: commit: Create a new file
5a7ef02 HEAD@{20}: checkout: moving from main to bugFix
5a7ef02 HEAD@{21}: clone: from https://github.com/UserName/Git_Training
```

Reset the current branch to HEAD@{3}


```
$ git reset --hard "HEAD@{3}"
```

HEAD is now at 61d5038 Merge


## ORIG_HEAD
Rebase saves the starting commit as ORIG_HEAD so you can reset to it

```
$ git reset --hard ORIG_HEAD
```

Follow this with rebase --abort to clean up after the reset

```
$ git rebase --abort
```


## BACKUP_01 TAG
You could add a BACKUP_01 tag on the branch before rebasing then restore using 

```
$ git reset --hard BACKUP_01
```

Remember tags must be unique and cannot be changed.

