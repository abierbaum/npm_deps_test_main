## Prep for Git commit

Download modules without building them
> rm -rf node_modules
> npm install --ignore-scripts 
> git add . && git commit -a   # Check in modules

## Now rebuild the packages and find build files with git status

Build the modules
> npm rebuild

Show the files created by the build (there might not be any), add then to .gitignore
> git status


## Packages Changed (removed, updated, etc)

Download modules without building them
> rm -rf node_modules
> npm install --ignore-scripts 
> git status #   see removed modules
> git add . && git commit -a   # Check in modules

## Now rebuild the packages and find build files with git status

Build the modules
> npm rebuild

Show the files created by the build (there might not be any), add then to .gitignore
> git status

