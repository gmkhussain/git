# git

## How to fetch all Git branches

```git fetch origin```
Now all branches will be locally.

```git branch -a```
See listed as remotes/origin/branch-name.

```git checkout -b seond_branch_name```








## Undo the most recent local commits

Undoing a commit is a little scary if you don't know how it works. But it's actually amazingly easy if you do understand. I'll show you the 4 different ways you can undo a commit.

##### option 1: git reset --hard

Say you have this, where C is your HEAD and (F) is the state of your files.

```cs
   (F)
A-B-C
    ↑
  master
```

You want to nuke commit C and never see it again and lose all the changes in locally modified files. You do this:

```git reset --hard HEAD~1```

The result is:

```cs
 (F)
A-B
  ↑
master
```

Now B is the HEAD. Because you used --hard, your files are reset to their state at commit B.


##### option 2: git reset

Ah, but suppose commit C wasn't a disaster, but just a bit off. You want to undo the commit but keep your changes for a bit of editing before you do a better commit. Starting again from here, with C as your HEAD:

```cs
   (F)
A-B-C
    ↑
  master
```

You can do this, leaving off the --hard:

```git reset HEAD~1```

In this case the result is:

```cs
   (F)
A-B-C
  ↑
master
```

In both cases, HEAD is just a pointer to the latest commit. When you do a git reset HEAD~1, you tell Git to move the HEAD pointer back one commit. But (unless you use --hard) you leave your files as they were. So now git status shows the changes you had checked into C. You haven't lost a thing!

##### option 3: git reset --soft

For the lightest touch, you can even undo your commit but leave your files and your index:


```git reset --soft HEAD~1```

This not only leaves your files alone, it even leaves your index alone. When you do git status, you'll see that the same files are in the index as before. In fact, right after this command, you could do git commit and you'd be redoing the same commit you just had.















## How to undo 'git reset'? OR redo

- ```git reflog```

Check log of all ref updates (e.g., checkout, reset, commit, merge). You can view it by typing:

- ```git reset 'HEAD@{3}'``
           OR
- ```git reset beb6904``` 

#### Output
```cs
a63791e (HEAD -> master) HEAD@{0}: reset: moving to HEAD~0
a63791e (HEAD -> master) HEAD@{1}: reset: moving to HEAD~1
d47dcd9 HEAD@{2}: reset: moving to HEAD~1
beb6904 HEAD@{3}: commit: Error Handling
d47dcd9 HEAD@{4}: commit: root -> <tdf>
a63791e (HEAD -> master) HEAD@{5}: commit: Submitting form data
6c65a49 HEAD@{6}: commit: Form validation
ea9f768 HEAD@{7}: commit: Select control validation
13ddc6d HEAD@{8}: commit: Displaying Error Messages
52a97a3 HEAD@{9}: commit: Validation with Visual Feedback
f70438c HEAD@{10}: commit: Tracking state and validity
```
















## Rename a Remote Git Branch
1. Verify the local branch has the correct name:
```
git branch -a
```


2. Next, delete the branch with the old name on the remote repository:
```
git push origin --delete old-name
```


3. Finally, push the branch with the correct name, and reset the upstream branch:
```
git push origin -u new-name
```
OR
```
git push origin :old-name new-name
```

Resetting the upstream branch is still required:
```
git push origin -u new-name
```

