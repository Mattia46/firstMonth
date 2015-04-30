# Installing Sublime

Sublime is a popular text editor that enables the use of shortcuts and plug-ins to speed up the process of writing code. We recommend it to our students because it is powerful yet easy to use and has a good community of users.

To install sublime go to [http://www.sublimetext.com/2](http://www.sublimetext.com/2) and download the appropriate file. Once the file is downloaded, run it and drag the sublime image to the Applications folder.

In order to run sublime from the command line, you will need to create a symbolic link. Type the following command into your command line terminal (You may need to prepend this with the 'sudo' command):

```
ln -s  "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

This process may fail with the following message if you have not yet installed Homebrew:

```
ln: /usr/local/bin/subl: No such file or directory
```

The best way to resolve this is to install [Homebrew](http://brew.sh/).

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Enter your password when asked, and follow any instructions presented in the terminal window.

Retry the symbolic link command above. 

After you have done this, you should be able to open your current directory in sublime by using the command:

```
subl .
```

Excellent unofficial documentation for Sublime Text can be found here: [http://docs.sublimetext.info/en/latest/intro.html](http://docs.sublimetext.info/en/latest/intro.html)

# Setting up your preferences

When you are writing code, you should keep to a particular style that remains uniform throughout your work. At Makers Academy, we recommend using 2 spaces for your indentation. You can set up sublime so that it automatically uses 2 spaces for tabs. The suggested settings can be found here:

[Suggested Sublme Settings](https://gist.github.com/maker-leo/5135649)

You can edit this in Sublime Text by pressing ``` ⌘ + , ```



Copy-paste the entire key into the license field (Help> add license) including the "begin license" and "end license" lines and use it to register SublimeText on your machine. It's free to evaluate but you should buy a license if you want to use it after Makers Academy.
```
----- BEGIN LICENSE -----
Evgeny Shadchnev
25 User License
EA7E-857876
5BCCA56E 27F7B4B4 364A288B C80BF7B4
500FDE3B B8C88E7A ACCDBAB4 1151EC5E
2BD90CCF E2FC7A97 C14A76A4 D1C3C4BE
D38C1D2D AB20EFBD 33051832 CB992D5C
ED938A53 2FED2EB6 D5A4D230 B5101CB1
2AF58C8D 147837CA 31B29826 0DFC9D0F
F8D53136 856AA854 EBAE89AF 837D03E7
99AB386F 2ACD1E7E 26CB6695 44E1CC7E
------ END LICENSE ------
```
