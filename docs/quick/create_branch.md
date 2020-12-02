# Creating a branch

## Scenario: Create a new working branch

1. You can create a branch from any other branch, but the most
   common is to branch from `main`.  Make sure you are in the
   correct branch to start
   ```
   $ git checkout main
   ```

1. Create your branch (all subsequent sections us `example`, but
   change it to the actual branch name you create).
   ```
   $ git branch example
   ```

1. Checkout your branch
   ```
   $ git checkout example
   ```

1. Do your work in the branch as regular changes; that is,
   change, add, commit.

1. If your branch needs to go to GitHub,
   ```
   $ git push origin example
   ```

1. Change back to `main` when done working in the branch.
   ```
   $ git checkout main
   ```
