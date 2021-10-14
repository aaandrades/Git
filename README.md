# Git

## Main commands

- git init: Starts the local repository.
- git add. : Add all files to control changes. He places them on the Stage.

GIT STATUS
- git status: Status of all files in the folder. Shows files that have been modified since the last commit and that have not been added to the repository. Branch in which we work, which files have been modified and which are ready to be uploaded.
- git status -s -b: Send a practical summary of the files that are modified accompanied by the branch information.

GIT COMMITMENT
- git commit: 'screenshot' of the state of the local repository.
  - git commit -m "commit message".
- git checkout -. : Restore files from the last commit
- git commit -am "message": Add and generate the commit all at once.
- git commit --amend -m "New message": Fix a commit.

GIT ADD
- git add * .png: add all png files in the current directory.
- git add "* .png": add all png files that are in the project.
- git add css /: add all the files inside the CSS folder.
- gitt add -A: Add all the files that were not added.
- git add <index.html, index.css>: list of files to add.

RESTART
- git reset .: Delete all files that are in the stage.

GIT LOG
- git log: traceability of all modifications to the project.
- git log --oneline: Log information in a shorter and more precise way.

GIT DIFF
- git diff: List of all modifications between the last commit and the current moment.
- git diff --staged: List of all modifications that are already added.

GIT PULL
  - git pull -u origin master

GIT FETCH
  It is used when the remote server has changes that the local one does not have.
ALWAYS PERFORM A FETCH OR PULL BEFORE THE PUSH TO KEEP THE CODE INTEGRITY. 

## Alias Creation

- git config --global alias.lg "log --oneline --decorate --all --graph" -> the name comes after the "alias"
  - git lg: same results.
- git config --global alias.s "status -s -b".
  - git s: same result.

## Git time travel
- git reset --soft #HashDelCommit: Mark commit Stage files
- git reset --mixed: Removed from the Stage
- git reset --hard: It is returned to the Commit, it removes everything that was done in the commit.
- git reflog: shows all the commit movement history
- git reset --hard #Hash of commit: Also restore commits that were lost.
- git checkout --filename: Revert changes made to a file before adding it to the stage.

## Branch
They are commit timelines
Merge: Unions from one branch to another.
  - Fast-forward: Automatic when there is no change in the main branch and there are no conflicts to join the branches.
  - Automatic joins: Git detects that the main branch had a change that the other branches do not have, but when doing the merge it joins it keeping the changes of the current line that it carries.
  - Manual: There is conflict between changes. Create the merge commit manually by the user.
  
Fast Forward: The most common, something is executed on the branch and joins
  - git branch branch_name: create a new branch
  - git branch: shows all branches and indicates which one is being worked on.
  - git checkout branch_name: switch to the chosen branch.
  - git diff branch_name other_branch_name: Shows the differences between each branch.
  - git merge name_branch_unite: On the master branch, it is executed to merge the content of the created branch.
  - git branch -d branch_name: remove the branch.
  
 Automatic Merge: Something is executed on the branch but the master keeps updating
  - git checkout -b branch_name: Create the branch and move to the branch.
  - git merge name_branch_unite: On the master branch, it is executed to merge the content of the created branch.

Merge Conflicting Joins: Two branches modify the same file.
  - Use atom extension to define what part of the code goes.
 Tags: A reference to a specific commit. Generally used to mark versions or releases.
  - git tag layer_name: Add Tag.
  - git tag -a V0.1.0 HasCommit -m "Alpha Version" 

## Git Stash
Box or Container where the temporary changes are saved to leave it in the last commit. It is good practice to always clear the stash after use.
  - Git stash: Create a new stash with all current job or process.
  - Git stash list: Shows all the WIP (Work in Progress) that the project has.
  - git stash pop: It is used to restore the files from the Stash and delete them.

## Git Rebase
When changes are made to the master that are used in our branch, git rebase stores the current changes in a temporary area, runs the commit timeline and reloads the files that we work in the temporary area.
<img src = "https://cms-assets.tutsplus.com/uploads/users/585/posts/23191/image/rebase.png" alt = "Markdown Monster icon"
     style = "float: left; margin-right: 10px;" />
Usually it is used to avoid conflicts with the merge, organize the commits.
  - git rebase master: Update with respect to the master branch
  GIT SQUASH
  - on the master allows to join commits.

## Publication Process
- git init
- git add.
- git commit -m "commit message"
- git remote add origin 'repository_url'
- git remote-v: associated sources
- git push -u origin master: It allows that the next time the command is executed it is not necessary to specify the branch.
- git push --tags: Upload all created tags. 
