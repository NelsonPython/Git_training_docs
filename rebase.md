# Rebase

Create a new branch and make changes

```
$ git checkout -b newFeature
Switched to a new branch 'newFeature'
 
$ nano my_new_feature.md
```

## Rebase

Fast-forward adding the changes made in newFeature to main

### Rebase main

```
$ git rebase main
Current branch newFeature is up to date.
```

### View log

```
$ git log --pretty=oneline  
 
c94b3a90f5508652b0f389c5a4d29a3bed8fdff5 (HEAD -> newFeature, bugFix) Merge
c22de5b0df2d70ce632e072e665f36f17e83e8d1 (origin/main, origin/HEAD, newImage, main) Attempt to add two new files
f4d3ecdccde96314ca72e3230cc6f4fb4733b323 Fix bug 1
813be9cc3d398639be946934cf821874e595de86 (bugFix/main) Create a new file
ef9f03315694e21695b14e3d7f2e9f993608fab1 Update README.md
8ecbd5143889e9efc3327fdb28fbdb7f3528fd8e Initial commit  
```

List the files.  ` my_new_feature.md ` appears in the list of files in the ` bugFix ` branch.

```
$ ls
README.md            bugFix1.md   my_first_merge.md  saveFile.md
bugBountyHunters.md  keepFile.md  my_new_feature.md
```

Checkout main.  my_new_feature.md also appears in the list of files for the main branch.

```
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

$ ls  
README.md            bugFix1.md   my_first_merge.md  saveFile.md
bugBountyHunters.md  keepFile.md  my_new_feature.md
```

### Commit
Rebasing combined files in newFeature and main.  Now, stage my_new_featuer.md and commit it.

```
$ git branch
  bugFix
* main
  newFeature
  newImage
 
 
$ git commit -m 'Add my new feature'
On branch main
Your branch is up to date with 'origin/main'.
 
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        my_new_feature.md
 
nothing added to commit but untracked files present (use "git add" to track)  $ git add my_new_feature.md
 
$ git add my_new_feature.md
 
$ git commit -m 'Add my new feature'
[main 572812e] Add my new feature
 1 file changed, 1 insertion(+)
 create mode 100644 my_new_feature.md
 
$ git log --pretty=oneline
572812e225bfa6eedb02153f67566cb85dca8d8d (HEAD -> main) Add my new feature
c22de5b0df2d70ce632e072e665f36f17e83e8d1 (origin/main, origin/HEAD, newImage) Attempt to add two new files
f4d3ecdccde96314ca72e3230cc6f4fb4733b323 Fix bug 1
813be9cc3d398639be946934cf821874e595de86 (bugFix/main) Create a new file
ef9f03315694e21695b14e3d7f2e9f993608fab1 Update README.md
8ecbd5143889e9efc3327fdb28fbdb7f3528fd8e Initial commit
  
$ git push
```

![](images/rebaseGit.png)


