# Installing Atom

Atom is a popular [open source](https://en.wikipedia.org/wiki/Open-source_software) text editor that enables the use of shortcuts and plug-ins to speed up the process of writing code. We recommend it to our students because it is powerful yet easy to use and has a good community of users.

To install Atom go to [http://atom.io](http://atom.io) and download the appropriate file. Once the file is downloaded, run it and drag the Atom image to the Applications folder.

When Atom installs, it automatically creates a [symbolic link](https://en.wikipedia.org/wiki/Symbolic_link) (also symlink) in your /usr/local/bin. This allows users to run Atom from the command line, like open your current directory, a specific file or just the editor in Atom by using commands like these:

```
atom . (opens current directory)

atom file.js (opens file)

atom (opens editor)
```
However, in case these are not available to you, you can create the symlink yourself. There are two ways of doing this, from the command line or straight from Atom.

##### From the command line

Type the following command into your command line terminal (You may need to prepend this with the 'sudo' command):

```
ln -s /Applications/Atom.app/Contents/Resources/app/atom.sh /usr/local/bin/atom
```

This process *may* fail with the following message if you have not yet installed Homebrew:

```
ln: /usr/local/bin/atom: No such file or directory
```

The best way to resolve this is to install [Homebrew](http://brew.sh/).

Enter your password when asked, and follow any instructions presented in the terminal window.

Retry the symlink command above.

##### From Atom

This is the easier option. Simply open Atom, click on the `Atom` menu and then on `Install Shell Commands`

![Atom menu](https://cloud.githubusercontent.com/assets/194400/7987327/ba954dce-0ad4-11e5-897a-19ed0f37ff41.png)

You should expect to see:

![Atom confirmation window](https://cloud.githubusercontent.com/assets/194400/7987297/88143464-0ad4-11e5-81f3-4ec7c1bdfc42.png)


## Setting up your preferences

When you are writing code, you should keep to a particular style that remains uniform throughout your work. At Makers Academy, we recommend using 2 spaces for your indentation. Atom uses 2 spaces for tabs by default and you can change your preferences by pressing ``` ⌘ + , ```.

A manual for Atom can be found here: [http://flight-manual.atom.io/](http://flight-manual.atom.io/)
