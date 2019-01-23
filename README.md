This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Purpose

This app demonstrates some inconsistencies in how react-dev-utils' `launchEditor` works with Visual Studio Code on Mac.

## Summary

If Visual Studio Code is opened from within the repo, and `yarn start` is run from within VS Code, opening a relative path works. In all other permutations that I've tested, it produces a confusing failure mode. (an empty document in an unexpected location)

## Scenarios

All of these assume that you have first cloned the repo and run `yarn` in it.

In each of the broken scenarios, a new document (and sometimes a new workspace) is opened called `src/App.js`

### Happy Path

- `cd` into the repo
- run `code .`
- open VS Code's terminal
- run `yarn start` in VS Code's terminal
- click the `src/App.js` button in the browser

### Broken Scenario 1

- close all VS Code workspaces
- `cd` into the repo
- run `yarn start`
- click the button in the browser

### Broken Scenario 2

- `cd` into the repo
- run `code .`
- from the original terminal, run `yarn start`
- click the button in the browser

### Broken Scenario 3

- `cd` to the parent directory of the repo.
- run `code stack-frame-playground`
- open VS Code's terminal
- run `yarn start` in VS Code's terminal
- click the button in the browser
