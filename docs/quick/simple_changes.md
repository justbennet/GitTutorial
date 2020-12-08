# Making direct changes

## Scenario: Make simple changes to file(s) locally

1. Check to make sure that you are starting from a good place.
   ```
   # Check whether you are working on the right branch
   $ git branch
   # Are there changes you need?
   $ git status
      ```

1. If you need to get some additions from `origin` (usually from
`main`, but sometimes not), then

```
$ # Pull the branch 
$ git pull origin
```

1. Add/commit any changes that need to be made; update as needed.

1. Make your changes.

1. Add your changes to staging.
   ```
   $ git add <filename(s)>
   ```

1. Commit the changes.
   ```
   $ git commit
   ```

   which will open your editor to enter the commit message.  Or, if
   you have a very short commit message, you can include it on the
   command line.
   ```
   $ git commit -m "A short commit message"
   ```
   
1. When working on lab repositories, you should _not_ be working from
   the `main` branch.  If you are working on your own repo, you may
   be doing so.  Once your changes are committed, and you are ready
   for others to see the work, you should push to GitHub
   ```
   $ git push origin <branch name>
   ```
