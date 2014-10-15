# Installing RVM

Sublime is a popular text editor that enables the use of shortcuts and plug-ins to speed up the process of writing code. We recommend it to our students because it is powerful yet easy to use and has a good community of users.

To install sublime go to [http://www.sublimetext.com/3](http://www.sublimetext.com/3) and download the appropriate file. Once the file is downloaded, run it and drag the sublime image to the Applications folder.

In order to run sublime from the command line, you will need to create a symbolic link. Type the following command into your command line terminal:

```
ln -s  "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

After you have done this, you should be able to open your current directory in sublime by using the command:

```
subl .
```
Excellent unofficial documentation for Sublime Text can be found here: [http://docs.sublimetext.info/en/latest/intro.html](http://docs.sublimetext.info/en/latest/intro.html)