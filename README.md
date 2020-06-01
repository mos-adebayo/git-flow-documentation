# git-flow-documentation

# Background

Git-flow is a branching model designed to get processes standardized. It uses the standard git commands. You can achieve “manually” all it does, it is just simpler to use and it prevents the use of incorrect branch and merging of branches appropriately.

# Semantic:
- It has two base branch **develop** & **master** (The names can be changed during setup)

- Features are created to adress distinct tasks.

- Hotfix are created when there is a minor fix for Production

- Release are created when we are ready to push a set of changes to production

# Setup:
- Run `git flow init` in the repository
- Follow the command prompts to set the default branch names


# How It Works:

## Working on Tasks
-	Tasks on Jira will be created as a feature branch 
    `git flow feature start feature_name`
-	Step one will create a branch name in this format `feature/feature_name`
-	All changes should be committed on this branch 
-	When you’re through with all changes. You can then push branch to repository and request for reviews 
-   Squash and merge branch on Github when branch is approved by reviewers

## Working on Hotfix
-	Update your **master** branch
-	Then create an hotfix branch 
    `git flow hotfix start hotfix_name`
-   Add all change and push branch for review    
-   After approval 
-   Finish hotfix branch (Before ending your hotfix, update your master branch)
    `git flow hotfix finsih hotfix_name`
-   Then follow the release step

## Creating a Release
_**Ensure your master & develop are up to date**_
-  Create a release branch 
   `git flow release start release_tag_name`
-  Test for changes and and ensure your **master** & **develop** branch are up to date before you finish a release
    `git flow release finish release_tag_name`   
-  The above command will merge changes to **master**, create a release **tag** and also merge changes to **develop** branch 
-  Then you will have to push changes up
   `git push (master)`
   `git push --tags`
   `git checkout develop`
   `git push (develop)`
   
   
### Reference
- https://readthedocs.org/projects/git-flow/downloads/pdf/latest/
