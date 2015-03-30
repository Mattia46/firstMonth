## Command-Line  – Basic commands

### Showing the date

The command line is fairly straight-forward: you type something in and you get something back. First off, type:

`date`

This shows us today's date, time and the time zone set by your computer:

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901095456_Screen%20Shot%202013-10-04%20at%2016.38.05.png "Date")

#### Listing files

Going back to the directory discussion from earlier, we see that we're in the "Desktop" directory. How do we list all of the contents of this directory?

`ls`

This stands for "list." This command will show everything in the "Desktop" directory:

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901340878_Screen%20Shot%202013-10-04%20at%2016.42.01.png "ls")

#### Printing working directory

We're in the "Desktop" directory, but what if we want to see the exact path of the directory that we're in?

`pwd`

This stands for "print working directory" and will give you the full path of the directory that you're working in. This is really useful for when we need to start working with file and folder locations.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901367914_Screen%20Shot%202013-10-04%20at%2016.42.32.png "pwd")

For those who many be unfamiliar with how paths work, they're identical to the way folders work in Finder. Let's say you have a "Documents" folder and inside that you might have a folder for all of your homework titled "Homework." Inside that folder you might have a separate folder for each subject. Then each subject is likely to have files. A path to a chemistry test might look like this:

` ~/Documents/Homework/Chemistry/term1test`

The tilde (~) at the beginning of the path represents your home directory (default directory for every user on this computer).

#### Changing directories

Okay, the "Desktop" directory is great, but what if I want to access other folders?

` cd ..`

The "cd" stands for "change directory" and the ".." tells us to move up to the parent directory. (Just for future reference, a "." represents "the directory I'm in" and ".." represents the parent directory.) Desktop's parent directory is usually the home directory and, as mentioned before, this is connotated by ~

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901427436_Screen%20Shot%202013-10-04%20at%2016.43.32.png "cd")

Do you remember how to list out the contents of this directory?

If you guessed "ls" you're correct.

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901465155_Screen%20Shot%202013-10-04%20at%2016.44.01.png "ls")

We can return to the "Desktop" directory now by typing:

` cd Desktop`

This is using the same "cd" command from earlier, but instead of telling it to move up to the parent directory by typing ".." we're telling it that we want to "change directory" into the "Desktop" directory. Now we're back in the "Desktop" directory:

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901492431_Screen%20Shot%202013-10-04%20at%2016.44.38.png "cd desktop")

#### Listing hidden files (using switches)

Earlier, we listed the public files in the "Desktop" folder - but what if we want to see the hidden files too:

` ls -lA `

This shows us all of the hidden files as well:

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901529371_Screen%20Shot%202013-10-04%20at%2016.45.19.png "ls -la")

In addition it shows them in the "long" format, that is, with extra information (size, creation date, owner, etc). The "-lA" parameter is actually a combination of two switches. We could have written the same command like this:

` ls -l -A `

However, if you're specifying multiple switches, you can combine them into one:

` ls -lA `

In this case, "-l" stands for "long format", and "-A" stands for all files.

#### Hidden files

Some files are hidden by default because they are used by the operating system and the users don't need to access them in most cases. However, "ls -lA" exists precisely because you'll want to access them on some occasions.

#### Creating files

While changing directories and listing contents is useful, how do we actually create files?

` touch worksheet `

The "touch" command creates an empty file with a given name. In this case it creates a file called "worksheet" in our current directory.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901727499_Screen%20Shot%202013-10-04%20at%2016.47.15.png "touch")

#### More about parameters

So far, I've shown you two examples of parameters for commands. A parameter is essentially an add-on to a command to make your instructions more specific. Earlier we showed you two ways of changing directories:

` cd .. `
` cd Desktop `

The ".." and "Desktop" are the parameters of the "change directory" command. Additionally, we showed you two "list" commands:

` ls`
` ls -lA`

The first one is simply the "list" command where as in the second one, we added the "-lA" parameter to specify that we wanted to see hidden files and we wanted the output to be in a long format. There are many parameters but for now, we'll just cover the most important ones.

The parameters that start with a hyphen (-) are often called switches.

#### Creating and destroying directories

So far all we've done is move around our file system and look at the contents. Let's now look at ways to make, move and remove files and directories. First off, let's start with:

` mkdir Example`

Any guess what this stands for? This is the "make directory" command with the added parameter of "Example" - it makes a new directory in whatever directory you're currently in with the name "Example"

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901839227_Screen%20Shot%202013-10-04%20at%2016.50.21.png "mkdir")

We can remove that directory just as easily as we created it:

` rmdir Example`

Here "rmdir" stands for "remove directory" with the parameter "Example" - telling it to remove the "Example" directory.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901863587_Screen%20Shot%202013-10-04%20at%2016.50.52.png "rmdir")

If, instead of a directory, we wanted to remove a file. We would simply use "rm" and the file name. We created an empty file using the "touch" command a while back, let's remove it now. Although please note that it is [difficult to recover files](http://superuser.com/questions/751756/is-rm-reversible) that have been deleted with `rm` so please be careful using this command:

` rm worksheet`

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901891615_Screen%20Shot%202013-10-04%20at%2016.51.21.png "rm")

Now let's try something else. Let's create a new directory called "SomeDir," change to that directory, create an empty file  called "someFile" and then change back out to its parent directory:

` mkdir SomeDir`
` cd SomeDir`
` touch someFile`
` cd ..`

What if we wanted to remove "SomeDir"? Let's try running "rmdir" again:

` rmdir SomeDir `

What? You got an error?

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380901939458_Screen%20Shot%202013-10-04%20at%2016.52.08.png "rmdir error")

That's because "rmdir" only works for empty directories. This is where some of those parameters will come in handy. Try this instead:

` rm -r SomeDir `

This uses the "rm" command with two parameters. The second parameter you know about. The first parameter (switch) is "-r" and tells the remove command to recursively remove all files within the directory as well as the directory itself.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902015447_Screen%20Shot%202013-10-04%20at%2016.53.19.png "rm -r")

Just to introduce you to a couple of other important "rm" parameters that you'll find useful:

` rm -i`

The "-i" parameter here stands for "interactive" and will prompt  you to confirm that you want to delete each file. This is really useful for when you have a lot of files but only want to delete a few of them.

Other times you don't care about protection and want to just force remove files. This is done with:

` rm -f`

This will remove any file even if it's "write protected", so please be extra careful with this command!

[NEXT](pills/command_line3.md)
