# Yarn workspace .bin path resolving bug

This project shows a sample to reproduce yarn workspace .bin path resolving bug

# How to run?

- Reproducable yarn version: 1.22.4

1. Install workspace with yarn

Symlinks
* packages/workspace-1/node_modules/.bin/myBin -> ../../../../node_modules/my_project_with_bin/cli_v1.js
* packages/workspace-2/node_modules/.bin/myBin -> ../my_project_with_bin/cli_v2.js

2. In `workspace-1` (depends on `my_project_with_bin/v1`)

When you run `yarn bin myBin`
➜ `/repos/yarn-workspace-bin-bug/node_modules/.bin/myBin`

3. In `workspace-2` (typescript `my_project_with_bin/v2`)

When you run `yarn bin myBin`
➜ `/repos/yarn-workspace-bin-bug/node_modules/.bin/myBin`

4. `yarn bin myBin` should indicate individual .bin folder for the project respectively.
