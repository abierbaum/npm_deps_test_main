## Workflow

### Unlock

> rm npm-shrinkwrap.json

Install and do things you want.

### Lock

Note: we use an .npmrc file with save-exact=true to make install use exact versions.  Also note that this will update the checked out modules as well.

> npm shrinkwrap --dev

### Precommit for git

(while locked; ie have npm-shrinkwrap.json file)

Download / update modules without building them

> rm -rf node_modules
> npm install --ignore-scripts
> git add --all node_modules
> git commit -a   # Check in modules

Now rebuild the full packages.

> npm rebuild

Show the files created by the build (there might not be any), add then to .gitignore

> git status

(optional) use git status to verify there are ignore build files

> git status --ignored


## Updating dependencies (CLI)

Use outdated to check which packages may need updated.  Then use
npm install with --save (or --save-dev) to updated those packages.

> npm install --save pkg@1.2.3

Verify that this updated both package.json and npm-shrinkwrap.json.

Similarly works for `npm uninstall`.

## Updating dependencies (package.json edit)

Use outdated to check which package may need updated.  Then edit the package.json file to add a new one or update.

Unlock
> rm npm-shrinkwrap.json

Install
> npm install --ignore-scripts
> npm shrinkwrap --dev
> rm -rf node_modules
> npm install --ignore-scripts
> ... normal git stuff above

Lock
> npm shrinkwrap --dev   # Add the shrinkwrap file back in

## Future

May want to use: https://github.com/uber/npm-shrinkwrap
shrinking tarballs: https://github.com/JamieMason/shrinkpack
