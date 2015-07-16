# Deployment Plan for
**[www.nickisnow.com](http://www.nickisnow.com)**

## Deployment Process

### Checkout Master Branch

From the command line:
1. cd **local repo directory**
   (**local repo directory** is the name of your projects' repo directory on your local machine)
2. git checkout master
3. git pull **github** master
   (**github** is the name given to the remote repo)
  1. Resolve any conflicts
    1.  Visit each conflicted file, resolve any conflicts and save files.
    2.  Once conflicts are resolved and saved, they need to be committed and another pull of remote is required.
      1.  $ git add -A
      2.  $ git commit -m ‘Relevant detailed commit message.’
      3.  $ git pull **github** master


From local Development, ```git push staging master``` will send files to the Staging server and GitHub repository. From local Development, ```git push production master``` will send the files to the Production server and GitHub repository. For reference, git hooks were set up per [Abhijit Menon-Sen's tutorial](http://toroid.org/ams/git-website-howto). Use descriptive, present-tense imperative commit messages, like ```git commit -a -m "add animation to header nav"```.  

Use annotated git tags (e.g., ```git tag -a v1.07 -m 'release v1.07'```) to increment versions as when a commit is significant enough to warrant a version incrementation. Push tags to server with ```git push production --tags```.
   
Use local branches from master for new features and bug fixes.

    git checkout master  # switches to master
    git branch <relevantBranchName>  # creates branch
    git checkout <relevantBranchName>  # switches to branch

Once the branch is ready for merging, merge and delete it.

    git checkout master  # switches to master
    git merge <relevantBranchName>  # merges branches
    git branch -d <relevantBranchName>  # deletes local branch