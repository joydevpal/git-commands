## Git Basic Commands

1. **git initialize**
```git init```
-----------------------------------------------------------------------------------
2. **git configuration**
```
git config --global user.email "user email"
git config --global user.name "user name"
```
-----------------------------------------------------------------------------------
3. **add files to git staging area**
```git add [filename.ext] | -A | .```
-----------------------------------------------------------------------------------
4. **check git status**
```git status```
-----------------------------------------------------------------------------------
5. **commit files with comment**
```git commit -m "message"```
-----------------------------------------------------------------------------------
6. **add remote location [github/bitbucket]**
```git remote add origin https://username@bitbucket.org/username/repo.git```
-----------------------------------------------------------------------------------
7. **how remote origin url**
```
git remote show origin
git config --get remote.origin.url
```
-----------------------------------------------------------------------------------
8. **download existing files from remote [ex. README.md]**
```git pull origin master [ add --allow-unrelated-histories if required ]```
-----------------------------------------------------------------------------------
9. **upload local files to remote [ex. project files]**
```git push origin branch [ex. master]```
-----------------------------------------------------------------------------------
10. **clone a repository to local folder**
```git clone repo-url [ex. https://username@bitbucket.org/username/repo.git]```
-----------------------------------------------------------------------------------

## Branch Manage

1. **show branches available**
```git branch (need atleast one commit to show branches)```
-----------------------------------------------------------------------------------
2. **create a new branch**
```
git checkout -b branchname (create and checkout the branch)
git branch branchname [ex. develop] (required atleast one commit to work properly)
```
-----------------------------------------------------------------------------------
3. **switch to another branch**
```git checkout branchname [ex. develop]```
-----------------------------------------------------------------------------------
4. **merge branch with master [must be in master]**
```git merge branchname [ex. develop]```
-----------------------------------------------------------------------------------
5. **delete a branch**
```git branch -d branchname [ex. develop]```
-----------------------------------------------------------------------------------

## Git Log

1. **show default log list**
```git log```
-----------------------------------------------------------------------------------
2. **show latest log by count**
```git log -[number] [ show last 2 if give 2 ]```
-----------------------------------------------------------------------------------
3. **show commit messages only**
```git log --oneline```
-----------------------------------------------------------------------------------
4. **show log by messages text (Case Sensitive)**
```git log --grep="text" [ex. readme]```
-----------------------------------------------------------------------------------
5. **show log by messages tex (Case Insensitive)**
```git log -i --grep="text" [ex. readme]```
-----------------------------------------------------------------------------------
6. **show log by author**
```git log --author="username"```
-----------------------------------------------------------------------------------
7. **search log by file content changed**
```git log -i -p -G "Hello"```
-----------------------------------------------------------------------------------

## Git Stash

Stash is basically used to manage temporary content save, retrive, delete etc

### **save stash** </br>
> ```git stash save "stash name"```
-----------------------------------------------------------------------------------
**show stash list** </br>
> ```git stash list```
-----------------------------------------------------------------------------------
**retrieve stash and apply to file**
```git stash apply stashid```
-----------------------------------------------------------------------------------
**delete a stash**
```git stash drop stashid```
-----------------------------------------------------------------------------------
**delete all stash**
```git stash clear```
-----------------------------------------------------------------------------------
**Show files changed after rebase**
```git ls-files -u```
-----------------------------------------------------------------------------------
## Manage Files

1. **view git command history ( actually these are any commands used in terminal, not only git )**
```history```
-----------------------------------------------------------------------------------
2. **show deleteable untracked files ( dry-run )**
```git clean -n```
-----------------------------------------------------------------------------------
3. **delete untracked files**
```git clean -f```
-----------------------------------------------------------------------------------
4. **delete folder from local repository ( recursive [include subfolder / files] )**
```git rm -r <folder-name>```
-----------------------------------------------------------------------------------
5. **delete blank folder**
```git clean -fd <folder-name>```
-----------------------------------------------------------------------------------
6. **exclude file from git index ( not physically deleted )**
```git rm --cached <file-name>```
-----------------------------------------------------------------------------------
7. **delete files**
```git rm <file-name>```
-----------------------------------------------------------------------------------
8. **go back to previous commit ( will see old files )**
```git checkout <commit-id>```
-----------------------------------------------------------------------------------
9. **restore / push old files to remote**
```git push -f origin <commit-id>:master```
-----------------------------------------------------------------------------------

## Advanced Branch Manage

1. **Create the branch on your local machine and switch in this branch**
```git checkout -b [name_of_your_new_branch]```
-----------------------------------------------------------------------------------
2. **Change working branch**
```git checkout [name_of_your_new_branch]```
-----------------------------------------------------------------------------------
3. **Push the branch on github**
```git push origin [name_of_your_new_branch]```
-----------------------------------------------------------------------------------
4. **You can see all branches created by using**
```git branch```
-----------------------------------------------------------------------------------
5. **Add a new remote for your branch**
```git remote add [name_of_your_remote] [name_of_your_new_branch]```
-----------------------------------------------------------------------------------
6. **Push changes from your commit into your branch**
```git push [name_of_your_new_remote] [url]```
-----------------------------------------------------------------------------------
7. **Update your branch when the original branch from official repository has been updated**
```git fetch [name_of_your_remote]```
-----------------------------------------------------------------------------------
8. **Then you need to apply to merge changes, if your branch is derivated from develop you need to do**
```git merge [name_of_your_remote]/develop```
-----------------------------------------------------------------------------------
9. **Delete a branch on your local filesystem**
```git branch -d [name_of_your_new_branch]```
-----------------------------------------------------------------------------------
10. **To force the deletion of local branch on your filesystem**
```git branch -D [name_of_your_new_branch]```
-----------------------------------------------------------------------------------
11. **Delete the branch on github**
```git push origin :[name_of_your_new_branch]```
-----------------------------------------------------------------------------------

## Additional Commands

1. **Delete sensitive files from all commit history**
```git filter-branch --force --index-filter "git rm --cached --ignore-unmatch PATH-TO-YOUR-FILE-WITH-SENSITIVE-DATA" --prune-empty --tag-name-filter cat -- --all```
```git push origin --force --all```
-----------------------------------------------------------------------------------