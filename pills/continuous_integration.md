Continuous Integration
======================

[CI](http://en.wikipedia.org/wiki/Continuous_integration) is a critical part of the professional developers stack - it's an automated process that will run a suite of tests any time code is submitted to a version control repo (such as GitHub) or when someone submits suggested code changes to that repo through a pull request.

At MakersAcademy we use CI in our engineering work (just as other professional software developers do around the world) and we also use it to monitor students progress as well as helping you get used to some of the tools that professional developers use.

The first time you'll experience CI will likely be during the Ruby weeks of the precourse when you start working with the Chris Pine exercises or the Ruby Kickstart challenges, when you submit pull requests to show us the progress you make.  You'll likely get an email telling you that the 'build' has 'failed' or 'passed'.  This tells us whether the code you've written has passed the automated tests that are checking it.  

In the case of the Chris Pine exercises, the CI build won't completely 'pass' until you've submitted every exercise for every chapter completely correctly and even then don't worry too much if the build fails as the CI (continuous integration) is not perfect.  In particular it currently can't handle any code that kicks off a call to the 'gets' method outside the body of the methods you create such as def `ask ... end` and `def roman_numerals ... end`.  When submitting your code there's no need to include the extra puts and gets at the end of the file, just submit the code that constitutes the method itself to see more of the build tests pass; but either way don't worry too much - the key thing is that you are working through the exercises and showing us your progress.

As you progress on your path to professional software developer you'll see many other instances of CI in the 12 weeks of the main course, and ultimately you'll become very comfortable with this important tool.
