## Workflow

### Update .npmrc

save-exact=true
registry=http://yogi.priority5.com:9090/

### Lock

Note: we use an .npmrc file with save-exact=true to make install use exact versions.  Also note that this will update the checked out modules as well.

> npm shrinkwrap --dev

### Unlock

> rm npm-shrinkwrap.json

Install and do things you want.

## Updating dependencies (CLI)

Use outdated to check which packages may need updated.  Then use
npm install with --save (or --save-dev) to updated those packages.

> npm install --save pkg@1.2.3

Verify that this updated both package.json and npm-shrinkwrap.json.

Similarly works for `npm uninstall`.

## Verify

Run shrinkwrap again to verify that we have the correct package versions

> npm shrinkwrap --dev

## Updating dependencies (package.json edit)

Use outdated to check which package may need updated.  Then edit the package.json file to add a new one or update.

Unlock
> rm npm-shrinkwrap.json

Install
> npm install

Lock
> npm shrinkwrap --dev   # Add the shrinkwrap file back in

## Future

May want to use: https://github.com/uber/npm-shrinkwrap
shrinking tarballs: https://github.com/JamieMason/shrinkpack
Watch out for this bug: https://github.com/npm/npm/issues/6855
