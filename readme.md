# Deployment Plan for [www.nickisnow.com](http://www.nickisnow.com)

## Deployment Process

### Checkout Master Branch

From the command line:

1. `cd **local repo directory**`
   (**local repo directory** is the name of your projects' repo directory on your local machine)
2. `git checkout master`
3. `git pull **github** master`
   (**github** is the name given to the remote repo)
  1. Resolve any conflicts
    1.  Visit each conflicted file, resolve any conflicts and save files.
    2.  Once conflicts are resolved and saved, they need to be committed and another pull of remote is required.
      1.  `git add -A`
      2.  `git commit -m ‘Relevant detailed commit message.’`
      3.  `git pull **github** master`

### Make Major Changes in a New Branch

1. `git branch **relevantBranchName**`  # creates a new branch
2. `git checkout <relevantBranchName>`  # switches to new branch
3. make changes as required

Once the branch is ready for merging, merge and delete it.

    git checkout master  # switches to master
    git merge **relevantBranchName**  # merges branches
    git branch -d **relevantBranchName**  # deletes local branch