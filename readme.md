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
6. `git push **github** **relevantBranchName**`  # pushes new branch to Github
7. `git checkout master` # switches to master
8. `git merge **relevantBranchName**`  # merges local branches
  1. Resolve any conflicts
8. `git push **stagingServer** master`
  (**stagingServer** is the name given to the staging server)
9. Test new feature extensively on staging server
10. If necessary, repeat steps 2-9

###  When Ready, Deploy Change to the Live Server and Delete New Branch.
1. `git push **github** master`  # updates master branch in remote repo
2. `git push **liveServer** master` #Deploys changes to live server
3. `git branch -d **relevantBranchName**`  # deletes new branch in local repo
4. Delete branch in remote repo
  1. Go to [github.com/.../branches](https://github.com/NickiSnow/portfolioProduction/branches)
  2. Click trash can icon to delete branch