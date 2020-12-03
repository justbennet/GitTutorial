# Working with Git

This will be a long page, as it will cover the regular tasks for which Git
will be used.  Those will include

* Getting an initial copy of the files
* Making one or more changes to a file or files
* Saving changes to your local copy
* Transmitting those changes to the GitHub repository.

You can get the full treatment (minus the bits about GitHub) about
what's happening here from the book
[Pro Git by Scott Chacon and Ben Straub](https://git-scm.com/book/en/v2).
The book is avaiable from that site as both a `.pdf` and in `.epub`
format.  I recommend everyone get a copy.

The chapter on
[Git Basics](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository)
corresponds to this section of this tutorial.

But first, you should configure your local Git so it knows who
you are and what some of your preferences are.  The main things
that people typically set are their real name, their e-mail
address, and which editor to use.  See the [Git configuration
page](https://justbennet.github.io/GitTutorial/git_configuration.html)
for some instructions for setting up Git on your computer.

## Getting an initial copy of your repo

As outlined in the
[Introduction](https://justbennet.github.io/GitTutorial/index.html)
this starts by making sure that you are up to date with what's in
the repository.

Since this is your first time working in this repository,
you need to _clone_ the repository.  Cloning a repository copies all of the
file from the `main` branch to your computer, where you can work on them.

This is done with the

```
$ git clone git@github.com:carpenterbennet/sample.git
```
again remembering that your GitHub username should replace `carpenterbennet`.

The above command will create a subdirectory called `sample` in whatever
directory you ran the `git clone` command.  You can tell Git to call the
local subdirectory something else, as in

```
$ git clone git@github.com:carpenterbennet/sample.git mind-lab-example
```
which would create a subdirectory called `mind-lab-example`.  The contents
will be the same, and Git will still know it came from the same place.

## Making changes

There are a number of things you an do to files that will be considered
changes: modify the contents, add a new directory/file, change the name, move
to a new directory, remove the directory/file.

### Changing a file directly on GitHub

We will start by modifying the existing `README.md` file.  We'll start
by making a change to the file on GitHub, then we'll come back to the copy
on your computer to make additional changes.

You need to be logged into GitHub, and your `sample` repository's page, which
will be something like `https://https://github.com/carpenterbennet/sample`.

By default, GitHub shows you the contents of the `README.md` file, so you
should consider that the 'landing page' for your repository (repo, hereafter).
For those wondering, the `.md` extension indicates a **Markdown** file, and
Markdown is a scheme for simplified formatting of text files.  For more
information on Markdown at GitHub (and elsewhere), see the [Mastering
Markdown](https://guides.github.com/features/mastering-markdown/) page.

You can edit files directly on GitHub, when that's appropriate.  In this case,
it is because we're only going to change the `README.md` file.  The `README`
has a shortcut pencil icon in the upper-right corner, but instead, please
click on the file name that appears above the displayed page.

That should change the view so there is a light blue line with the name of the
person who made the last change (you, in this case), a commit ID, when it
was committed, a button to view the History of this file.  Further down, there
will be a grey bar that says how many lines in the file, how big it is, and
on the right will be two buttons (Raw and Blame), a pencil icon, and a trash
can icon.

Since we want to make changes, use the pencil icon to open the file in the
GitHub editor and change the contents to look like this.

```
# Keilholz MIND Lab Git tutorial

This repository is an example for practicing with Git.

```

If you have a tall screen, you may need to scroll down to see the green
Commit changes button (and the Cancel button). Above those buttons, you'll
find two boxes under the heading **Commit changes**.  Think of the first
line like you would the subject line of an e-mail message and the box
below it for the optional extended description as the body of the message.

Because we want to illustrate what these look like, enter

```
Making the `README` informative
```

in the upper box and

```
Modified the description.

Entering an extended description for purposes of illustration.
```

Click the **Commit changes** button, which will save the changes and display
the modified file.  Sometimes the rendered page is not what you want to see,
so you can use the **Raw** button to see unrendered text.  Use the browser's
back button to go back to the rendered page.

From the rendered page, click on the **History** button, and that should take
you to a listing of the commits that have modified this page, with the newest
listed at the top.  On the right, the commit ID is typically a blue,
multicharacter string.  Clicking on it will change to a window where you can
see the old text (with the pink background) lines prefixed with a `-` (minus)
and the new text (with the green background) lines prefixed with a `+`.

In this case, this isn't particularly helpful, but consider the case where
someone has gone through and changed a variable name in 15 places....

Also note the light blue box at the top that contains the commit message.
If the commit message outlines in English what the changes were intended to
do, then someone checking on them can more easily figure out whether the
code changes do so.

### Changing a file from your computer

When you change things using the GitHub interface, most actions are performed
with buttons.  Now we'll look at how to do the same thing from the command
line, which will be far more convenient if you are modifying and testing
Matlab (or Python, C++, et al.) code.

Open a window and change to the directory in which you cloned the repository.
This will be `sample` if you didn't supply a different directory name when
you cloned.

You've made changes to the code at GitHub, so what you have on your local
computer is not what you have on GitHub.  This situation will most commonly
arise when working with others who might change code without you knowing.

It is always a good idea to start by _pulling_ changes made at GitHub.
So, change to the directory into which you cloned the GitHub repository.
Then use

```
$ git pull origin main
```

to get the changes that were made directly on GitHub.  You'll see some
kind of progress report.

The simplest changes are those that are made directly to the `main`
branch.  "What's that _branch_ thingy?" you ask.  A branch is
basically a different version.  We'll get to creating new branches
later, but for now, you are working with your own files in your
own repo, so you can work directly with `main` and not step on
the toes of others or have yours stepped on.

So, use whatever editor you like and add a line of text to the
`README.md` file.

```
An additional line added on my computer.
```

So, now you have a modified file.  To see what `git` thinks of
this,

```
$ git status
On branch main
Your branch is up-to-date with 'origin/main'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Git is telling you that you are on the `main` branch, that it is
up to date with the one on GitHub (the `origin/main`).  Then it tells
you that you have changes but they are not _staged_ for commit, which
we'll come back to shortly.  Next it tells you what you can do about
that.  The first option is what you need to do to stage the changes,
and the second option is how to reverse the changes.  Then it it
tells you which file(s) were changed.

Before we `add` or `commit`, it's often useful to look at what changes
have actually been made.  I've found some I thought were made missing,
and I've also found changes I did not intend.  Git provides access to
the standard Unix utility `diff`, which shows the differences between
two files.  Our current state of things is that we have a modified file
that has not been added or committed, so we can

```
diff --git a/README.md b/README.md
index c48a3fe..c646b9f 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,4 @@
-# sample
\ No newline at end of file
+# Keilholz MIND Lab Git tutorial
+
+This repository is an example for practicing with Git.
+
```

Changes are shown as lines that would be removed (shown with a prefixed
`-` sign) and lines that would be added (shown with a prefixed `+` sign).

After review, we are satisfied the changes are good, so

```
$ git add README.md
```

You can use shell wildcards (e.g., `*.md`, `README.*`), and Git will
not add unchanged files.

For those who remember working with paper and pencil, you can think
of the local directory as being your desktop, with documents strewn
about.  There is a basket called `staging`, and when you are done
making changes to a document, you put it in the `staging` basket.

If you decide to change something in the `stage` basket, you edit
it, which implicitly makes a different version, which must be `add`ed
again to supercede the version in the `stage` basket.

When you've made sufficient changes to documents, you `commit` them,
which is a bit like calling your trusty minion, who takes the stuff
from `stage`, types it neatly, and puts in in the cabinet called
`repo`.

```
$ git commit
```

That will open the editor you set in your preferences for you to
type the commit message.  Think of the commit message as being
like e-mail:  The first line should be a short summary, like
the subject line, then skip a line, and if a more detailed
explanation will be helpful for people, enter it on the third
and following lines.

The editor may or may not do line wrapping automatically.  I
encourage people to keep their lines shorter than 76 characters
so they will display nicely in a standard terminal window.
Exiting the editor and saving the changes will finish the commit.

If the change was minor, you can include the commit message
on the command line, as in

```
$ git commit -m "Fixing minor typos in README"
```

which will bypass the editor and commit with a one-line message.

Once files have been committed, you need to `push` your changes to
GitHub.

```
$ git push origin main
```

You _do not_ have to push your changes after every `commit`.  I often
do not.  I tend to commit more often than I really need to, and when
I get things to a relatively finished state, only then do I push to
GitHub.  That makes keeping track of the changes and outlining them
in the commit messages easier for me.

If you want to reorganize your files, Git has its own versions
of the `rm` (remove) and `mv` (move) commands from Linux.  You
should use those in preference to the Linux commands so Git
will register the changes properly.

To summarize, the standard working routine is

1. Update from the source
1. Make changes
1. Add the changes
1. Commit the changes
1. Repeat the previous three steps as often as makes sense
1. Push the changed repo to GitHub

