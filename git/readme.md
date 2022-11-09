# Configure the author name and email address to be used with your commits.
git config --global user.name "Sam Smith"
git config --global user.email sam@example.com

# To create a new tag execute the following command
git tag <tagname>

# Push the tag to the branch
git push origin <tagname>

# To delete a tag execute the following
git tag -d <tag_name>

# To delete a remote tag
 git push --delete origin <tag_name>

# List tags
git tag

# List tags on remote
git ls-remote --tags <remote>

# Sublime Merge Git Rebase steps. All steps initiated by <command> <shift> <p>

## update local branch with latest updates 
pull --ff-only 

## checkout your branch
checkout devops-322

## rebase 
rebase L ML-2765

## push your branch updates to remote
push devops-322 origin --force-with-lease

