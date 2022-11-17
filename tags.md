# Tags

Tags are used to mark certain commits.  Tags cannot be changed and they must be unique.  Suppose you could delete a tag.  Git is a distributed source control system.   What if someone pulled a copy of the repo, then you made a change and changed the tag?  They would not know about the change and their code would be out of sync with your updates.

Git supports two types of tags: lightweight and annotated.  A lightweight tag is generally used as a temporary tag that points to a specific commit.  Annotated tags are stored as full objects in the Git database.  They have a checksum.  Annotations include the tagger name, email, and date along with a tagging message.  Annotated tags can be signed and verified with GNU Privacy Guard (GPG).   Use the git tag -a command to add the tag.  Use -m to add a message. 

## Add an annotated tag

```
$ git tag -a v1.0 -m "version 1.0"
 
$ git show v1.0
tag v1.0
Tagger: UserName <User@email.com>
Date:   Tue Sep 20 13:16:41 2022 -0700
 
version 1.0
 
commit f42c72c92b7bf79eb105778d9ec453dac7d7ca0c (HEAD -> main, tag: v1.0, np/main)
Author: UserName <34105635+UserName@users.noreply.github.com>
Date:   Tue Sep 20 13:01:11 2022 -0700
 
Create remote.md
 
diff --git a/remote.md b/remote.md
new file mode 100644
index 0000000..30a6227
--- /dev/null
+++ b/remote.md
@@ -0,0 +1,3 @@
+# Remote
+
+This file was created on Github.
```
