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

## Resolving merge conflicts

A merge conflict will arise when there are two branches, usually
`main` and some other, and both branches have changes to the
same part of the same file committed.  So, for example, if

Let's say I update my local `main` branch, then I create a new
branch called `showme`.

```
$ git pull origin main
$ git checkout -b showme
```

I then make a change to a line in the README file -- the heading
-- in the `main` branch using the GitHub editor after doing that.

Then, once again in my local copy, where I have `showme` checked
out, I change the same line in a different way.

```
[ make change to README heading ]
$ git add README.md
$ git commit -m "Updated README heading"
```

Finally, I merge `showme` into my local `main`.

```
$ git checkout main
$ git merge showme
```

The result of this is that there are two versions of `main`
each starting from a common place but with different changes.

When I got to pull the changes from GitHub, the buzzer sounds.

```
$ git pull origin main
From https://github.com/carpenterbennet/sample
 * branch            main       -> FETCH_HEAD
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

That is telling us that Git marked the places in `README.md` where
there are two different changes vying to be The Right One, and we
have to go pick one.

So, the contents of `README.md` is now

```
<<<<<<< HEAD
# Sample for Git Tutorial
=======
# Sample Repository

This repository is a sample for the Git Tutorial
>>>>>>> c7c32e680768deb2bbbfce1f9afbdcbef7c5b351
```

The part between the line `<<<<<<< HEAD` and the line of
equal signs are what is in the version of `main` on the
local computer, and the part between the equal signs is
what is in GitHub.

At this point, this is just like making any other change.
You need to make the file look like how you want it by
deleting all the unwanted text.  You could choose to
keep one block or the other and delete the delimiting
lines and the unwanted block, or you could choose to
make something entirely different.

Once you've modified `README.md` so it's the way you like
it, you just save it, and

```
$ git add README.md
$ git commit -m "Resolving conflicting headings"
$ git push origin main
```

In this case, if I had instead pushed the `showme` branch to
GitHub and submitted the PR, all this would have been avoided.
That's one really good reason to make the merges at GitHub
rather than locally.

