# Undoing changes

There are two common situations that you might want to get back to
where you were before.  The first is when you add something to be
committed, but then change your mind about doing so.  This is
different from wanting to make additional changes, this is actually
taking the file back out of the 'stage basket' entirely.  It will
then go back to being 'untracked changes'.

To illustrate, let's look at the contents of a `README.md` file.

```
# Sample for Git Tutorial

This repository is a sample for the Git Tutorial
```

Now, we edit `README.md` to read

```
# Sample for Git Tutorial

This repository is a sample for the Git Tutorial.

It can be changed.
```

If you run `git status`, you will see

```
On branch main
Your branch is up-to-date with 'origin/main'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
which tells you what to do to `add` or get back the original.

OK, so suppose you `git add README.md` but then change your mind?
`git status` again tells you how to recover

```
On branch main
Your branch is up-to-date with 'origin/main'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
```

so you would run

```
$ git reset HEAD README.md
```

to remove the changes from those that will get committed.  If you
want to go all the way back to the way it was before you started
making changes, you would then

```
$ git checkout README.md
```

As a note, if you had added several files and wanted to pull them
all out, you could do that by leaving the filename off the `reset`.

```
$ git reset HEAD
```

## Undoing commits

Looking at the StackOverflow question:
[How do I undo the most recent local commits in
Git?](https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git)
you will see that 21,933 people said it was a useful question, and the
first answer 23,856 people thinking it was helpful.  You
would not be alone asking how to do this.

In the last segment, you no doubt noticed that the top line
marking the merge conflict had `HEAD` in it.  `HEAD` is a
_pointer_ to a specific Git commit ID.  For those not used
to pointers from programming, a pointer is essentially an alias,
and in this case it is to a specific commit ID.  Every branch
name is also a pointer to a commit ID.

Each time you make a commit, the ID for the current state of
your working copy changes.  When you push, or pull, or merge,
you are changing the ID to which the branch name points.

So, from the current ID to which `HEAD` points, you can go back
one ID by referring to `HEAD~1`, two IDs by referring to `HEAD~2`,
etc.  `HEAD~` is equivalent to `HEAD~1`.

So, as the author of that StackOverflow post says, to go back
one commit, you would

```
$ git reset HEAD~
```

That undoes Git's memory of the changes committed, but it
_leaves the files in their changed state_ and removes them
from the staging basket.  You would need to change any files
that need changing, then `add` all the files that should be
committed, and then

```
$ git commit -c ORIG_HEAD
```
which will find your previous commit message and open it in
the editor.  If no change to the previous message is needed,
`-C` (capital 'C') will resuse it as is.
