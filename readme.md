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

### Make Major Changes in a New Branch and Test on Staging Server

1. `git branch **relevantBranchName**`  # creates a new branch
  (**relevantBranchName** is the name given to the new branch)
2. `git checkout **relevantBranchName**`  # switches to new branch
3. make changes as required in local repo files
4. `git add -A`
5. `git commit -m ‘Relevant detailed commit message.`
6. `git push **github** **relevantBranchName**`
7. `git push **stagingServer** **relevantBranchName**` **Does this work?**
  (**stagingServer** is the name given to the staging server)
8. Test new feature extensively on staging server

### When Ready, Merge and Delete New Branch and deploy change to the live server.

1. `git checkout master` # switches to master
2. `git merge **relevantBranchName**`  # merges branches
  1. Resolve any conflicts
3. `git branch -d **relevantBranchName**`  # deletes new branch
4. `git push **github** master`  # updates remote repo
5. `git push **liveServer** master` #Deploys changes to live server