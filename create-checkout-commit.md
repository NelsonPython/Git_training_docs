# Create, Checkout, Commit

Git is a powerful tool.  When making changes, it is important to understand what you are changing and why.  Visualizing how Git works may give your mind's eye a clear picture of what's going on under the hood.  These examples are highlights from this Tutorial - Visualize How Git Works which has an interactive, animated interface so you can see the flow.  

A branch is a pointer to a commit.  Commits are identified by a sha; however, for sake of simplicity, this diagram shows the original commit as C0.  C1 is the first commit.  C2 is the second commit.  The main branch is pointing to C2.  HEAD is the symbolic name for the currently checked out commit.  It normally points to a branch name.  In this example, HEAD is pointing to main.  This is indicated by the star, main*.  

## Create a new branch

A branch includes the most recent commit and all parent commits.  Create a new branch:

``` 
git branch newImage
```

The newImage branch points to C1 along with the main branch.  HEAD is still pointing to main so you are on the main branch.


If you commit without changing to the newImage branch, then only the main branch will update.  

```
git commit
```

Now the newImage branch is pointing to commit 1 and the main branch pointing to commit 2

## Checkout a branch
You must checkout a new branch before committing it.

```
git checkout newImage

git commit
```

Now, newImage is pointing to commit 2 and main is pointing to commit 1.

Create and checkout at the same time
In the first section of this course, you used this shortcut command to simultaneously create a new branch and check it out:

```
$ git checkout -b <branch name>
```

## Commit
A commit in a git repository records a snapshot of all the (tracked) files in your directory.  You used this command to commit all the files and write a message to the log.

```
$ git commit -a -m 'Commit all the files'
```
