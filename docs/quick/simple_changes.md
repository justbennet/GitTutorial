# Making direct changes

## Scenario: Make simple changes to file(s) locally

1. Check to make sure that you are starting from a good place.
   ```
   $ git status
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
   
