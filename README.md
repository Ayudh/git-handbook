# git-handbook
Tips and tricks of Git

`git config --global crendential.helper manager` -> to use windows credential manager to store login details

git config --local user.email "ghari@g.com" --> .git/config
Everything is an object in git
.git/objects -> dir will be created with first two chars of commit hash as folder and inside it a file with remaining char as file name 
git branch <newbranch> && git checkout <newbranch> --> git checkout -b <newbranch>

.git/refs/heads -> contain local branch files -> each branch file contains a single commit hash -> all a branch is a pointer to a commit hash

a branch is not a sequence of commit. Its just points to a commit.
a commit has a parent

git status

add a file to stage and then if changed, the new change will not be staged.

git add -p || --patch -> for interactively add to stage
git add -i || --interactive

index is the staging area, place where which chages are to be added to next commit

git log --oneline --decorate --all --graph

git merge <branch name> -> merge branch to the current branch we are in

git merge --abort -> cancel the merge if any conflicts

git rerere -> setting

git rebase <branch name> -> rebases branch to the current branch and shows any conflicts
git rebase --continue -> to continue after resolving conflict
git rebase --no -ff -> no fast forward i.e., has a commit of merged similar to gi t merge new commit

git rebase -i -> interactively edit history -> change commit message -> squash multiple commits -> remove commit

git bisect

git checkout <filename> -> to discard the changes

git commit --amend -m "new commit message" -> changes previous commit message -> a new commit hash is generated bcz commit is changed
git commit --amend -> adds staged changes to previous commit

git log --stat -> shows the files changed in each commit 

git reset --soft <commit hash> -> resets and keeps changes in staged area
git reset --mixed <commit hash> -> resets and keeps changes not in staged area only in working directory
git reset --hard <commit hash> -> resets and removes changes in tracked file but not untracked files
git clean

git reflog -> shows the work history incase we lost the changes with reset hard
git checkout <commit hash> -> detached head state
from above branch create a new branch -> git branch backup

git revert <commit hash> -> reverts to a particular commit by adding a new commit -> this doesn't change the history -> safe if the changes are pushed to remote and pulled -> does the opposite actions to bring the state to a reverted commit

git cherry-pick <commit-hash>

git stash -> to carry changes from branch to branch
----------
git stash save "message"
git stash list
git stash pop
git stash clear
git stash apply <stash id>
  
git reset hard undo
git fsck –cache –no-reflogs –lost-found -> check git fsck man page

`git add file.txt --force` to add a file which is in .gitignore

`git rm --cached file.txt` to remove

`git update-index --skip-worktree <file>` instruct git not to touch this file for changes

`git update-index --no-skip-worktree <file>` undo the above command

`git clean -df` to remove untracked files
`git checkout .` to revert changes

`git clean -df && git checkout .` to clean the working directory

git edit old commit - https://stackoverflow.com/a/2719636
