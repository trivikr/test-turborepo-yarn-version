# test-turborepo-yarn-version

This is a test repository to check if the `yarn` version is correctly detected by `turbo`.

## Pre-requisites

* Install Node.js
* Run `corepack enable` to help Node.js detect yarn version

## Steps to reproduce

Run `yarn turbo build`
```console
$ yarn --version
1.22.22

$ yarn turbo build
yarn run v1.22.22
$ /Users/trivikr/workspace/test-turborepo-yarn-version/node_modules/.bin/turbo build
turbo 2.1.2

• Packages in scope: app-a, app-b, pkg-a, pkg-b, tooling-config
• Running build in 5 packages
• Remote caching disabled
pkg-b:prebuild: cache hit, replaying logs c89be603e815ebcc
pkg-b:prebuild: 
yarn run v1.22.22
warning package.json: No license field
$ echo "Executing pre-build step..."
pkg-b:prebuild: Executing pre-build step...
✨  Done in 0.04s.
app-b:build: cache hit, replaying logs 211c7d7e8035ff5b
pkg-a:build: cache hit, replaying logs 0ab7f84c29ec3c36
app-b:build: 
yarn run v1.22.22
warning package.json: No license field
$ mkdir -p dist && echo "Your application output!" > dist/app-output.txt && echo "Application B is built!"
app-b:build: Application B is built!
✨  Done in 0.05s.
pkg-a:build: 
yarn run v1.22.22
warning package.json: No license field
$ echo "Building at the speed of Turbo." > output-file.txt && cat output-file.txt
pkg-a:build: Building at the speed of Turbo.
✨  Done in 0.04s.
pkg-b:build: cache hit, replaying logs 76ca724502afbacb
pkg-b:build: 
yarn run v1.22.22
warning package.json: No license field
$ echo "Executing pre-build step..."
pkg-b:build: Executing pre-build step...
$ echo "Welcome to the Turboverse." > output-file.txt && cat output-file.txt
pkg-b:build: Welcome to the Turboverse.
✨  Done in 0.05s.
app-a:build: cache hit, replaying logs 0d657c2f008d301b
app-a:build: 
yarn run v1.22.22
warning package.json: No license field
$ mkdir -p dist && echo "Your application output!" > dist/app-output.txt && echo "Application A is built!"
app-a:build: Application A is built!
✨  Done in 0.04s.

 Tasks:    5 successful, 5 total
Cached:    5 cached, 5 total
  Time:    216ms >>> FULL TURBO

✨  Done in 1.32s.
```

The `yarn` version is correctly detected by `turbo` as `v1.22.22`.