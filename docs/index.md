# Why Git and GitHub

Git has become the predominant program for managing computer code.  It's
basically a system to enable one or more people to keep track of what
changed in their code over time, from first draft on.  It enables you
to make different versions so you can work on updates or fixes or new
capabilities without breaking what you already have.

GitHub is a web site that enables you to share your code, and it provides
a fairly convenient way to communicate with other people who use your code.
They can submit questions and report problems there; they can help you fix
broken things; they can add bells and whistles; whatever.

It's also a sort of de rigeur thing if you want people to think you're cool
and are part of the 'coder culture', which is itself cool.

Mostly, though, you might find it really useful in your work.  That's what
matters.

# A day in the life

Let's assume for the moment that you start work and you need to add a file
that performs some new numerical operation, say, a noise filter for
electrode data.

This is a new file, so you know that no other files depend on it.  That makes
things easier right away.

You change into the project directory, open Matlab, write furiously until
exhaustion.  You take a break, run it several times testing for edge cases,
how does it deal with unexpected values as inputs, etc.  You get it to a
state where it works.

Next you add it to the list of things that have changed since you started.
Today, it's just one file; on other days it could be many.

Next you add all the changes to the project, and along with putting the file
there, you sign your work, and you add to the change log -- the code version
of the lab notebook -- an explanation of what your changes do.  For something
simple, this might be a few words:  "Fixed numerous typos".  For something
more complex, this might be more extended.

Next you send your changes to GitHub where they become part of the larger
project.

