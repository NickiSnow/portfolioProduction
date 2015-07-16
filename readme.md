# Deployment Plan for
**[www.nickisnow.com](http://www.nickisnow.com)**

## Deployment Process

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