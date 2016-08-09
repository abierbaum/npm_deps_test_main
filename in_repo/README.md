## Prep for Git commit

Download / update modules without building them

> rm -rf node_modules
> npm install --ignore-scripts
> git add --all node_modules
> git commit -a   # Check in modules

## Now rebuild the packages and find build files with git status

Build the modules
> npm rebuild

Show the files created by the build (there might not be any), add then to .gitignore
> git status

Optionally use git status to verify there are ignore build files
> git status --ignored

