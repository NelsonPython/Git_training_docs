# Navigating the git commit stack

Relative references or relative refs can be used to navigate Git.  The following two symbols move up or down through the commit stack:  

^ - move up one level

```
$ git checkout main^

$ git checkout HEAD^

```

~<num> - move up a number of times.  In this example, move up from HEAD 3 times

```
$ git checkout HEAD~3
```


Suppose you are at main and attempt to checkout main^

```
git checkout main^
$ git checkout main^
Note: switching to 'main^'.
 
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.
 
If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:
 
  git switch -c <new-branch-name>
 
Or undo this operation with:
 
  git switch -
 
Turn off this advice by setting config variable advice.detachedHead to false
 
HEAD is now at 7bc9d99 Fix bug 1
```
  
### Checkout main
  
```
$ git checkout main
Previous HEAD position was f4d3ecd Fix bug 1
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
```

### Check out HEAD

```
git checkout HEAD
$ git checkout HEAD
Your branch is up to date with 'origin/main'.
```

### Check out the 'Fix bug 1' commit

```
$ git checkout HEAD^  
 
Note: switching to 'HEAD^'.
 
You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.
 
If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:
 
  git switch -c <new-branch-name>
 
Or undo this operation with:
 
  git switch -
 
Turn off this advice by setting config variable advice.detachedHead to false
 
HEAD is now at f4d3ecd Fix bug 1
```

### Where is HEAD?

```  
$ git log --pretty=oneline  
 
f4d3ecdccde96314ca72e3230cc6f4fb4733b323 (HEAD) Fix bug 1
813be9cc3d398639be946934cf821874e595de86 (bugFix/main, bugFix) Create a new file
ef9f03315694e21695b14e3d7f2e9f993608fab1 Update README.md
8ecbd5143889e9efc3327fdb28fbdb7f3528fd8e Initial commit
```

Check out the initial commit
  
```
$ git checkout HEAD~3
Previous HEAD position was f4d3ecd Fix bug 1
HEAD is now at 8ecbd51 Initial commit
  
$ git log --pretty=oneline
8ecbd5143889e9efc3327fdb28fbdb7f3528fd8e (HEAD) Initial commit
```
  
  
