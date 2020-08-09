## Git Basic Commands

**git initialize**
> `git init`

**git configuration**
> `git config --global user.email "user email"` </br>
> `git config --global user.name "user name"`

**add files to git staging area**
> `git add [filename.ext] | -A | .`

**check git status**
> `git status`

**commit files with comment**
> `git commit -m "message"`

**add remote location [github/bitbucket]**
> `git remote add origin https://username@bitbucket.org/username/repo.git`

**how remote origin url**
> `git remote show origin` </br>
> `git config --get remote.origin.url`

**download existing files from remote [ex. README.md]**
> `git pull origin master [ add --allow-unrelated-histories if required ]`

**upload local files to remote [ex. project files]**
> `git push origin branch [ex. master]`

**clone a repository to local folder**
> `git clone repo-url [ex. https://username@bitbucket.org/username/repo.git]`


## Branch Manage

**show branches available**
> `git branch (need atleast one commit to show branches)`

**create a new branch**
> `git checkout -b branchname (create and checkout the branch)` </br>
> `git branch branchname [ex. develop] (required atleast one commit to work properly)`

**switch to another branch**
> `git checkout branchname [ex. develop]`

**merge branch with master [must be in master]**
> `git merge branchname [ex. develop]`

**delete a branch**
> `git branch -d branchname [ex. develop]`


## Git Log

**show default log list**
> `git log`

**show latest log by count**
> `git log -[number] [ show last 2 if give 2 ]`

**show commit messages only**
> `git log --oneline`

**show log by messages text (Case Sensitive)**
> `git log --grep="text" [ex. readme]`

**show log by messages tex (Case Insensitive)**
> `git log -i --grep="text" [ex. readme]`

**show log by author**
> `git log --author="username"`

**search log by file content changed**
> `git log -i -p -G "Hello"`


## Git Stash

Stash is basically used to manage temporary content save, retrive, delete etc

### **save stash** </br>
> `git stash save "stash name"`

**show stash list**
> `git stash list`

**retrieve stash and apply to file**
> `git stash apply stashid`

**delete a stash**
> `git stash drop stashid`

**delete all stash**
> `git stash clear`

**Show files changed after rebase**
> `git ls-files -u`

## Manage Files

**view git command history ( actually these are any commands used in terminal, not only git )**
> `history`

**show deleteable untracked files ( dry-run )**
> `git clean -n`

**delete untracked files**
> `git clean -f`

**delete folder from local repository ( recursive [include subfolder / files] )**
> `git rm -rf <folder-name>`

**delete blank folder**
> `git clean -fd <folder-name>`

**exclude file from git index ( not physically deleted )**
> `git rm --cached <file-name>`

**delete files**
> `git rm <file-name>`

**go back to previous commit ( will see old files )**
> `git checkout <commit-id>`

**restore / push old files to remote**
> `git push -f origin <commit-id>:master`


## Advanced Branch Manage

**Create the branch on your local machine and switch in this branch**
> `git checkout -b [name_of_your_new_branch]`

**Change working branch**
> `git checkout [name_of_your_new_branch]`

**Push the branch on github**
> `git push origin [name_of_your_new_branch]`

**You can see all branches created by using**
> `git branch`

**Add a new remote for your branch**
> `git remote add [name_of_your_remote] [name_of_your_new_branch]`

**Push changes from your commit into your branch**
> `git push [name_of_your_new_remote] [url]`

**Update your branch when the original branch from official repository has been updated**
> `git fetch [name_of_your_remote]`

**Then you need to apply to merge changes, if your branch is derivated from develop you need to do**
> `git merge [name_of_your_remote]/develop`

**Delete a branch on your local filesystem**
> `git branch -d [name_of_your_new_branch]`

**To force the deletion of local branch on your filesystem**
> `git branch -D [name_of_your_new_branch]`

**Delete the branch on github**
> `git push origin :[name_of_your_new_branch]`


## Additional Commands

**Delete sensitive files from all commit history**
> `git filter-branch --force --index-filter "git rm --cached --ignore-unmatch PATH-TO-YOUR-FILE-WITH-SENSITIVE-DATA" --prune-empty --tag-name-filter cat -- --all` </br>
> `git push origin --force --all`
