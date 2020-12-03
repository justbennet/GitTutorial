# Git branches

When you want to make changes that may be substantial, or take the
code in a different direction, or that you just want to keep
separate for a while (or, I suppose, forever), you can use a
branch for that.  Branches are also for experimental work.

In many traditional software projects, branches are often used
to write new features into the software.  They can also used
to 'freeze' the software at a particular point when a new
version is to be released so that any new features that get
added will go to the next release, but bugs in the current
things can be fixed.

One example that might apply to some of your code would be
if you had some Matlab function calls that got removed
from recent versions of Matlab.  You might make a branch
to update all those calls to the current functions, then
save the old version for people with, say, Matlab older
than R2020a but have a branch for people with R2020a and
newer.

You would want at some point, to decide how to handle
situations like that.  More on management strategies
elsewhere.  Let's look at how to work with them rather
than when and why.

## Creating a branch

You can check what branches exist with

```
$ git branch
* main
```

The asterix indicates that is the currently active branch.

We'll create a branch called `new_stuff` with

```
$ git branch new_stuff
$ git branch
* main
  new_stuff
```

That creates it, but you are still in whichever branch
you were in (on) when you did so.  You have to `checkout`
a branch to work in it

```
$ git checkout new_stuff
Switched to branch 'new_stuff'
$ git branch
  main
* new_stuff
```

You can combine creating and changing to a new branch with

```
$ git checkout -b new_stuff
Switched to a new branch 'new_stuff'
```
Once you have a branch checked out, any changes made, added,
and committed will get saved to that branch and not to any
others.

## Updating a branch

Say you are working on some modifications to the lab's library
collection.  Someone else is also working on changes.  Say
they added a function that was not there when you created
your branch, but you want to use it in your new stuff.  You need
to update your branch from `main`.

First, checkout `main`, then `pull` the changes to `main`.

```
$ git checkout main
$ git pull origin main
```

Next, checkout the branch on which you are working, then
`merge` the changes from `main` into the branch.

```
$ git checkout new_stuff
$ git merge main
```

That should add any changes to `new_stuff` made to `main`
since `new_stuff` was created.

You can, of course, reverse this and merge your branch into
`main`.  You would first make sure that `main` is up to date,
then `merge` new stuff into it.  Finally, you would be `push`ing
to `main` with no review.

```
$ git checkout main
$ git pull origin main
$ git merge new_stuff
$ git push origin main
```

However, it is probably better to instead `push` your branch
to GitHub,

```
$ git push origin new_stuff
```

and create a Pull Request (PR) from that branch to `main`.
