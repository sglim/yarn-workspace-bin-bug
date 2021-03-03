# Yarn workspace .bin path resolving bug

This project shows a sample to reproduce yarn workspace .bin path resolving bug

# How to run?

- Reproducable yarn version: 1.22.4

1. Install workspace with yarn

2. In `project_a` (typescript 4.0.2)

When you run `yarn bin`
➜ `/repos/yarn-workspace-bin-bug/project_a/node_modules/.bin`

When you run `yarn bin tsc`
➜ `/repos/yarn-workspace-bin-bug/node_modules/.bin/tsc`

3. In `project_b` (typescript 4.2.2)

When you run `yarn bin`
➜ `/repos/yarn-workspace-bin-bug/project_b/node_modules/.bin`

When you run `yarn bin tsc`
➜ `/repos/yarn-workspace-bin-bug/node_modules/.bin/tsc`

4. `yarn bin tsc` should indicate individual .bin folder for the project respectively.

