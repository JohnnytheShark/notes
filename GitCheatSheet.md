# Git Cheat Sheet 

## Listing Branches 
    git branch
List branch names found in repository

If you want to limit history use the name of the branch git branch <branch-name>

## Viewing Branches and Their Commits 
    git show-branch
provides more detailed output than the git branch command. 
    git show-branch
list the local branches. 
When you use the command -r it shows the remote tracking branches 
with -a it shows all local and remote branches 


## Checking out branch
    git checkout branch
Used to checkout a certain branch

Another use of git checkout is to restore files back from the tip or HEAD commit 
    git checkout branch~4 index.js
This would restore the state for a specific file four commits back form the tip or HEAD commit

can also be used to recover a deleted file
    git checkout deletedfile

Checking out a file that is named the same as a branch: 
     git checkout -- file-with-same-branch-name.js

## Experimental Options: 
    git switch branch
allows you to switch to that branch 
    git restore [options] file
allows you to restore operations on file states

## Merging and differences 
You can merge into a new branch with: 
    git checkout -m <branchname>
To see the differences use: 
    git diff

## Creating new branch: 
    git checkout -b <new branch name>

## Going back to a prior commit: 
    git checkout <commit-hash>

## Deleting Branches 
    git branch -d branch

## Commits
A commit is a snapshot capturing the current state of a repository at a moment in time.

Commits should only happen when no semantic gap appears in history.

You can create a commit summary and detailed message for the summary by using -m option multiple times: 
    git commit -m "Summary" -m "Details of Summary" 

    git commit --help 
Gives you all the options that you can use.

You can use
    git show --pretty=fuller
To see additional details about a given commit

HEAD - always refers to the most recent commit on the current branch. WHne you change branches Git automatically updates HEAD 

ORIG_HEAD certain operations, such as merge and reset, record the previous version of HEAD in ORIG_HEAD just prior to adjusting it to a new value. You can use ORIG_HEAD to recover or revert to the previous state or to make a comparison.


    git tag -a Tag
Annotated tags can be used when you're createing a specific release version for your project 

### School of thoughts
Fine Grained - every changed is tracked
Didactic - only your best work is committed

    git revert commit 
doesn't alter the existing history within a repository. It adds new commit to the history. Typically regarded safe.
example: git revert main~3

git commit --amend 
Typically used to fix typos right after a commit. However, it can also be used to amend any file or files in the repo, and can add or delete files as part of the new commit.

git reset command changes your repo and working directory to a known state.

git cherry-pick commit applies the changes introduced by the named commit on the current branch. It will introduce a new distinct commit. Strictly speaking, using git cherr-pick doesn't alter the existing history within a repo, instead it adds to the history. 

Another common use for cherry-pick is to rebuild a series of commits by selectively picking a batch from one breanch and introducing them onto a new branch

Example: 
$ git checkout main
    $ git cherry-pick my_dev~1     # Y
    $ git cherry-pick my_dev~3    # W
    $ git cherry-pick my_dev~2    # X
    $ git cherry-pick my_dev      # Z

## Branch Names Dos and Don'ts: 
- You can use a forward slash to create a hierachical name scheme. However the name cannot end with a slash
- No slash-separated component can begin with a dot: feature/.new is invalid
- The anem cannot start with a minus sign
- The name cannot contain two consecutive dots .. 
- No whitespaces 
- Cannot include a character that has special meaning: ~ ^ : ? * or and open square bracket [


## Logs
To see former commits use
    git log
or 
    git log --oneline

To see more details you can use 
    git show <commit hash>

Typically you can use the first 7 characters of the hex numbers in most commands

git log commit can be useful for viewing the history of a branch.

We can also format the messages: 
 git log --pretty=format:"%an was the author of commit %h, %ar with%nthe commit titled: [%s]%n" \
   > --abbrev-commit main~9..main~7

The --graph option wiht git log prints out a textual representation of the repository's commit history.



## gitk
THe gitk command can draw a picture of a repository DAG representing the repository's history


## Ranges of Commits 
start..end

## Merges 

## Aborting a merge after it has finished: 
git reset --hard ORIG_HEAD 

To find merge base between two or more branches you can use 
git merge-base 


