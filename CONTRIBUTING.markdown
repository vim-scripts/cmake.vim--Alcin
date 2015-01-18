# Contribution guidelines #

## Reporting issues ##
Make sure that what you are experiencing is actually an error and that it lies
with cmake.vim and not a misconfiguration of your CMake build.

### Questions ###
If you have a question be sure to read [the documentation][] first.
Often you will find the answer to it there.
[the documentation]: ./doc/cmake.txt

### Description ###
As with bug reports everywhere else:

* state the action(s) you took
* explain what outcome you expected
* describe the actual result

You will also need to report which operating system you encountered the issue on
and which shell you used (type `echo $SHELL` in your terminal if you are unsure).

### Reproducing ###
Unless you ran in to a [heisenbug][], it should be possible to reproduce the
bug in a testing environment. 
[heisenbug]: http://en.wikipedia.org/wiki/Heisenbug

## Pull requests ##

### Branching
**Work from and create pull requests on `develop`, not `master`.**

`master` always represents the latest release since that is the way homeshick
updates itself. The `develop` branch is where work is done for the next
release version of homeshick.

### Code style ###
TODO

Use the supplied [editorconfig][] file. Most editors have [editorconfig
plugins][] to apply these settings.
[editorconfig]:         http://editorconfig.org
[editorconfig plugins]: http://editorconfig.org/#download

### Content ###
**Every PR should only contain one feature change, bug fix or typo correction.**

Commits should be atomic units of work, if they are not you should rebase them
so that they are (typo corrections from a previous change for example do not
justify a commit).

### Description ###
The PR should clearly describe what problem the change fixes.
A feature addition with no justification and use-case will be rejected.

### Testing ###
Unless the code-change is a refactor, you should always add unit tests.  When
fixing a bug there should be a new test case that fails with the old code and
succeeds with the new code. When introducing a new feature, it should be
tested extensively, a single test case will not suffice.

Note that bats does not fail a test case when using double brackets.
To assert variable values and file existance you *must* use single brackets!

Also consider negative test cases (e.g. what happens when a non-existing
castlename is passed as an argument?).

You can read about the details of the testing framework
in the [testing documentation]().
[testing documentaion]: ./TESTING.markdown
