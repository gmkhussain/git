# git

## How to fetch all Git branches

```git fetch origin```
Now all branches will be locally.

```git branch -a```
See listed as remotes/origin/branch-name.

```git checkout -b seond_branch_name```








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




