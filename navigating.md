# Navigating the git commit stack

Relative references or relative refs can be used to navigate Git.  The following two symbols move up or down through the commit stack:  


```
^ - move up one level

git checkout main^

git checkout HEAD^
```

```
~<num> - move up a number of times.  In this example, move up from HEAD 3 times

git checkout HEAD~3
```

