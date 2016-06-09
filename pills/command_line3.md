#### Copying and moving files

Copying directories is quite straight-forward. Let's create a new directory, change into it and create an empty file:

` mkdir SomeDir`
` cd SomeDir`
` touch someFile`

Now, if we wanted to create an exact copy of "someFile" we'd use this command:

` cp someFile newFile`

The copy command is "cp" and takes two parameters. The first is the file to be copied and the second is the new file that will be created from it. If we list the contents of the directory now, we'll see both files:

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902096069_Screen%20Shot%202013-10-04%20at%2016.54.46.png "cp")

Now what if we wanted to move "newFile" somewhere else?

` mv newFile ../newFile`

The "mv" or "move" command takes two parameters. The first is the file to be moved (and its location) and the second is where the file will be moved to. In our situation, we didn't have to specify the path of "newFile" because it was already in our working directory, but we did need to specify the path of where we wanted to move it because it was outside of our working directory. We used ".." again, just like we did with the "cd" command, to specify that we wanted to move the file to our parent directory.

If we now change directories to the parent and list the contents, we'll see the file.

` cd ..`
` ls`

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902147077_Screen%20Shot%202013-10-04%20at%2016.55.28.png "mv")

Did you notice how I specified the name "newFile" when declaring the destination as well? This means that we can actually use the "mv" command to rename files without even moving them.

Let's go back into our "SomeDir" directory to bring newFile back over and I'll show you what I mean:

` cd SomeDir`
` mv ../newFile newFile`
` ls`
![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902198448_Screen%20Shot%202013-10-04%20at%2016.56.28.png "mv 2")

If we now run "mv" without providing a new destination, we can simply rename the file:

` mv newFile newerFile`

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902216118_Screen%20Shot%202013-10-04%20at%2016.56.47.png "mv 3")

#### Viewing files

For this next section, open up a text editor. If you're using a Mac, the TextEdit application will work fine (or use [Atom](installing_atom.md) that we'll be using for the rest of the course).  If you're on Nitrous you can use the built in text editor.  If you are using TextEdit on the Mac do ensure that it is set to 'plain text' rather than 'rich text'.  In TextEdit you can do this on the Format menu: Format → Make Plain Text.  Note that it is very important to use plain text formatting.  Rich text formatting (such as in MS Word) introduces extra symbols that will cause problems down the line.

Once you are set up in the 'plain' text editor of your choice, type in the following text into the document (followed by an empty new line):

` There are 10 types of people in this world`


Save the file into the "SomeDir" folder that we've been using and call it "someText"

To make sure everything worked according to plan, let's list the files in "SomeDir":

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902530774_Screen%20Shot%202013-10-04%20at%2017.02.01.png "ls")

Everything looks good, but how would we view that text document directly from the command line?

` cat someText`

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902569814_Screen%20Shot%202013-10-04%20at%2017.02.43.png "cat")

The "cat" command literally means "concatenate" (just a fancy word for "combine") as combining files is its primary purpose, but it has many other uses - such as the one I just showed you.

One of those many uses is to create short text documents right in the browser. If we type:

` cat > someMoreText`

You'll see a blinking cursor on the next line for you type some text in. Go ahead and type:

`Those who understand binary and those who don't`

then hit return

then type: `^C`

The ^C interrupts the command and is done with Ctrl+C.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902655200_Screen%20Shot%202013-10-04%20at%2017.04.03.png "cat > ")

Let's list the files again, just to make sure everything is fine:
![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902676299_Screen%20Shot%202013-10-04%20at%2017.04.19.png "cat > ls")

We can combine (or "concatenate") these two files with:

` cat someText someMoreText > combined`

Now if we view that file with:

` cat combined`

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902743304_Screen%20Shot%202013-10-04%20at%2017.05.31.png "cat combined")

Ta-da. It's magic.

#### Viewing large files

What if we need to work with larger amounts of text? Copy the following text into another text document and save it in "SomeDir" as "longText.txt"

*Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.*

*It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).*

*Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.*

*The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from "de Finibus Bonorum et Malorum" by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.*

*There are many variations of passages of Lorem Ipsum available, but the majority have suffered alteration in some form, by injected humour, or randomised words which don't look even slightly believable. If you are going to use a passage of Lorem Ipsum, you need to be sure there isn't anything embarrassing hidden in the middle of text. All the Lorem Ipsum generators on the Internet tend to repeat predefined chunks as necessary, making this the first true generator on the Internet. It uses a dictionary of over 200 Latin words, combined with a handful of model sentence structures, to generate Lorem Ipsum which looks reasonable. The generated Lorem Ipsum is therefore always free from repetition, injected humour, or non-characteristic words etc.*

As usual, let's double-check to make sure everything worked correctly:

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902785911_Screen%20Shot%202013-10-04%20at%2017.06.16.png "ls")

Now, type this:

` less longText.txt `

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902821716_Screen%20Shot%202013-10-04%20at%2017.06.50.png "less")

Using the "less" command, you're able to scroll up and down with your keyboard to view the entire document. When you're ready to finish viewing, just type "q"

You can also just view the first few lines of the file by using:

` head -3 longText.txt `

The "head -3" command tells the computer that we want to view the first 3 lines of the longText.txt file. You can change 3 to any number you want, depending on how much you want to view. If you leave it out, it will default to the first 10 lines.

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380902854944_Screen%20Shot%202013-10-04%20at%2017.07.25.png "head 3")

#### Tailing files

We can view the last few lines of a file just as easily with:

` tail -3 longText.txt `

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380903155155_Screen%20Shot%202013-10-04%20at%2017.12.27.png "tail")

"Tail" also has a really useful parameter that it's worth mentioning: -f. When we move along to actually running programs, you'll often want to watch the log of what's happening behind the scenes in your programming. To do this, you can use the "-f" parameter with "tail" like this:

` tail -f log.txt `

OSX, the operating system on the Mac, uses a number of log files. You can peek at what your computer is doing by running

`tail -f /private/var/log/system.log `

First you'll see the last 10 messages. If you quit or start some application, your Terminal will be updated with new messages describing what's going on. To stop tailing the log, press Ctrl-C.

#### Getting Help

There will be any number of situations where you'll have a question about what command to use or wonder what a command is truly designed for. Let's see how to handle those situations.

`man ls `

The "man" or "manual" command takes a parameter of another command to provide you more information about it. In the example here, we want to know more about the "ls" command.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380300031530_Screen%20Shot%202013-09-27%20at%2017.40.15.png "man")

By reading through this, we can find out what all of the parameters are, the description and various other pieces of information for using it correctly.

The square brackets in synopsis mean that the parameter or switch is optional. For example, in case of less, you can omit any switch because all of them are shown in square brackets. The same applies to the file(s) that should be given after the switches: if you specify the directory or file name, it will be listed but if you don't, current directory will be used by default. Finally, three dots at the end of the synopsis mean that you can specify one or more files to list.


### Command-Line 1 – More advanced commands

#### Streams

Every program on your computer has at least three "standard streams" associated with it. Streams are just channels used to connect the input and the output of the program to the environment (usually the terminal). The keyboard is referred to as an input stream. By reading from the input stream your program can read what you have typed on the keyboard. The screen is referred to as an output stream. By sending data to the output stream, a program can print something on the screen. There is also an error stream that is usually sent to the display as well but is used only to print error messages.

The input stream is usually called stdin and has number 0. The output stream is stdout (#1) and the error stream is called stderr (#2).

![alt text](http://upload.wikimedia.org/wikipedia/commons/thumb/7/70/Stdstreams-notitle.svg/535px-Stdstreams-notitle.svg.png "stout")

(source: [Wikipedia](http://en.wikipedia.org/wiki/File:Stdstreams-notitle.svg)).

Why do we need to know all of this? Because we can redirect the streams, connecting different streams from different programs. This will allow us to perform some sophisticated tasks.

#### Pipes and Redirection

Pipes allow you to redirect streams. For example:

`cat combined | less`

The "|" symbol, also known as a "pipe," passes the output stream (what would normally be printed on the screen) of the command to the left of the pipe to the input stream of the command on the right. So in this example it's passing the output of the file "combined" into the "less" command that we learned about earlier.

This will make "less" take the input from the input stream as opposed to opening the file given as an argument. The output of `cat combined` will not be shown on the screen at all since we redirected the output stream to the input stream of `less`.

Let's consider another example. Suppose you have lots of files in the current directory and you would like to view them using the `less` command instead of just printing thousands of lines on the screen. You can redirect the output of `ls` to `less`.

`ls -lA | less`

Then you'll be able to move up and down the text as if the output were a normal file. Later in this lesson we'll see many more examples of redirection.

In addition to redirecting the output stream of one program to the input stream of another one, we can redirect the output to a file. Consider this example.

`cat combined > newCombined`

The greater-than symbol writes the output stream of the command on the left to the file on the right. Wait, we didn't have a "newCombined" file before, did we? Let's check the folder's contents now.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380904304651_Screen%20Shot%202013-10-04%20at%2017.31.33.png "terminal")

What happened is that we wrote the output of "combined" into a new file that we named "newCombined".

#### Displaying What You Want (Wildcards)

As our programs get larger and we have to start wading through large numbers of files, the time will come when we want to have more control over how we look at the system. Let's look at a helpful way to do this.

If we look again at the contents of our SomeDir folder, you should see this:

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380904351261_Screen%20Shot%202013-10-04%20at%2017.32.22.png "ls")

We have 1 text file and 6 other files. With only 7 files, finding what we want is pretty easy. But what if we had 7,000 files? Wildcards is the answer.

This is how you'd list just the text files:

`ls *.txt`

The asterisk acts as a wildcard, telling the computer to only show you the files that end in .txt. You can use the wildcard in various scenarios. Take a guess at what each of these do before running them:

`ls new*.txt`
`ls *`
`ls *n*`

And obviously you can use asterisks with any command, not just "ls" because that's the built-in feature of the command-line (or the bash shell, strictly speaking), not of any particular command.

Another way to list specific files is by using the "find" command. It looks like this:

`find . -name "*.txt" -print`

This command works a lot just like normal English. It's saying: "find all files, starting with the current directory, with any name that ends in .txt and print it to the screen." Another cool feature of the "find" command is that, if you have additional directories inside the directory you search in, it will go into those directories as well and continue the search. Therefore, this is how we'd print out every text file in our home directory:

`cd ~`
`find . -name "*.txt" -print`

The first command you already know - to change directories into your home directory. The second command is just using the find command again to tell it to go through and print all text files in the Home directory, plus any other directories inside your home directory.

So, knowing everything that we know now, how could you create a text document that lists out every mp3 file in your Music directory? (Not everyone uses and stores their music the same way, so you may not be able to find any mp3 files on your computer, but you should understand how it works.)

`cd ~/Music`
`find . -name *.mp3 -print > myMusic.txt`

Both wildcards and "find" are useful for displaying specific files, but what if we want to look inside those files? If you remember from earlier, we've created a few text files in SomeDir. What if I wanted to look at only those files with the word "binary" inside the file? That's where grep comes in.

`grep binary *.txt`

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380904552368_Screen%20Shot%202013-10-04%20at%2017.35.17.png "wildcard")

The "grep" command takes two parameters: the first is what you want to search for (in this case, the word "binary") and the second is what files you want to search through (in this case, the file "combined").

It's also possible to use a pipe to redirect output to grep, so that it worked with the text from the input stream instead of the file we gave it as an argument. Let's print all text files in the home directory that have "readme" in their name.

`find ~ -name "*.txt" -print | grep README`

This command will find all files but instead of printing them, all filenames will be redirected to grep. Grep, in turn, will only print those filenames that include "readme". Try it to see how it works (don't forget the quotes around *.txt, they are important).

#### Very brief mention of regular expressions

Strictly speaking, grep is taking not a string, but a regular expression as an input.

A regular expression describes the pattern that you are looking for. It's similar to wildcards but it's orders of magnitude more powerful. For example, this command would look for all files that have numbers in the filename. You can't do this with wildcards but you can with regular expressions.

`find ~ -name "*" -print | grep "\d+"`

(You may need to use `"\d\+"` expression if this command doesn't work on your machine.)

We will cover regular expressions later in the course.

#### Counting words

Okay. We can find the files we want and get a fair amount of information, but there are still a few more tricks to make things easier.

For example, let's say that our longText.txt file needs to be fewer than 500 words. There's an easy way to check that:

`wc longText.txt`

The "wc" command gives us the "word count" - among some other things.

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_ymW6Sl1t69J_p.52567_1380907084407_Screen%20Shot%202013-10-04%20at%2018.17.56.png "counting workds")

You can see that this command gaves us back 3 numbers: 9 - 492 - 3005. These are the line, word and character counts for the longText.txt file.

And again, you can use pipes to count the output of other programs. How many readme files do we have in the home directory?

`find ~ -name "*.txt" -print | grep README | wc -l`

First, find will find all text files, then grep will select those that have "readme" in their name and "wc -l" will count how many lines were given to it by grep. On my computer I have 24 readme files in my home directory.

[NEXT](command_line4.md)
