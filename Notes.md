### Git Branches

To get the list of all branches
```bash
git branch
```
To create a new branch
```bash
git branch <branch_name>
```
To select a branch
```bash
git checkout <branch_name>
```

To create and select the new branch at same time
```bash
git checkout -b <branch_name>
```

This will rename the current selected branch 
```bash
git branch -m <new name of branch>
``` 

To delete a branch  (Note: selected branch can't be deleted)
```bash
git branch -d <branch_name>
```
<br>

### Stashing

**If we do not want to commit right now but want to save our changes temporarily then we use `stash` command**





To Save the changes temporarily somewhere
```bash
git stash
```

To apply the changes which we make, we use 
```bash
git stash apply
``` 

<br>

### Merging Branches :

this will merge the given branch to the current selected branch
```bash
git merge <branch_name>
```
	
- Note : first we have to select the branch in which we want to merge( for eg. : `main` branch ) and then run above command to get merge


### Merge Conflict

- When we make the changes in the same file (for eg. - `file1.txt`) from two branches and both braches are unaware of that changes
then at this time i will go and try to merge these branches, then it will get confused that should i keep the changes in `line1` which is done by `feature_branch` or keep the changes done by `master` branch
and this will lead to **Merge conflict**.


- Now when we find a merge conflict then we need to manually address it.

- Now when there is merge conflict in a file then it will look something like this
    ```
        <<<<<<< HEAD
        hello world !
        hello world again 👩🏻
        this is the content from master branch
        =======
        this is the content added from feature_branch
        >>>>>>> feature_branch
    ```
- the content which is above the `====` sign , is from the current branch and below this sign is from another branch 

- then we have to manually keep the changes which we want to keep and then finally commit it.

<br>

### GitHub :

To check that from which repository i am connected
```bash
git remote -v
```

To clone a remote repository into my local machine
```bash
git clone <repo-link>
```

It will fetch the latest changes from remote
```bash
git fetch <origin>
```
	
	
**Now if we bring the remote changes :**

it will fetch the latest changes from remote but will not merge
```bash
git fetch <origin>
```

to merge the changes after fetching
```bash
git merge origin/main
```

it will fetch and merge the changes in one command only
```bash
git pull origin 
```
    

it will push the changes i made in my local machine to current remote repository
```bash
git push origin
```

Now if we want to make Open Souce Contribution then we have to do following steps :

1. we have to fork a repository in which we want to contribute into our github by clicking on the `fork` button of that repo.
2. we clone it to our local machine to add some code / or we can do this on github itself , and commit those changes
3. we push our changes(using `git push` command) into our forked repository on github.
4. Now we have to make a request to the owner to take my changes, which request is called `PULL REQUEST`.