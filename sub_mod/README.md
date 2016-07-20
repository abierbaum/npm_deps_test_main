## Submodule Prep

Download modules without building them
> cd node_modules; rm -rf .
> npm install --ignore-scripts 
> cd node_modules && git add . && git commit -a   # Check in modules

## Now rebuild the packages and find build files with git status

Build the modules
> npm rebuild

Show the files created by the build (there might not be any), add then to .gitignore
> git status

