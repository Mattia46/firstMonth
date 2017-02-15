#### Permissions

You can control the access to every file on your computer: some files can be read-only, some files can be not available to read to some users, etc. Everyone (a person or a program) using a computer has to identify themselves as some user. You can find out what your name is by using this command:

`whoami`

Every file on a unix-based system has three classes of permissions: "user", "group" and "others". Every class has three permissions: read, write and execute. This allows us to give, for example, read and write access to the owner of the file, only read access to the group it belongs to and no access at all to all other users. Let's discuss classes and permissions in more details.

"User" class determines the permissions that the owner of the file has. Every file on a Unix-like system has some user as an owner. A file can have at most one owner and not more.

"Group" class determines the permissions that apply to a group of users. Any user can belong one or more groups of users (but doesn't have to). For example, if there are several users who access the computer only remotely, they may be organised into a special group that has limited privileges.

"Others" class applies to all users that don't fall into the other two classes.

The "read" permission allows a file to be read. When applied to a directory, it allows to list directory's contents, that is, to see the list of files.

The "write" permission allows to write to a file, or, in case of a directory, it allows creating, deleting and renaming files.

The "execute" permission allows to execute a file. For example, in order to run a program, it must have the "execute" permission to be set. If you create a ruby script, you won't be able to run it directly unless it's executable (has the "execute" permission). We'll see an example later when we'll be discussing something called a "shebang".

If a directory has the "execute" permission, then you can change into it and access files provided that the files' permissions allow this and you know their names. If you don't know their names, you'll need the "read" permissions to find out directory contents first.

In Unix, the permissions are not inherited, so if a directory has a "read" permission, it doesn't imply that the files in it are readable as well.

#### Viewing permissions

You can view the permissions by listing the directory in a "long" format.

`ls -l`

This will produce a list of files and some extended information about them.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381137966416_Screen%20Shot%202013-10-07%20at%2010.25.53.png "ls -s")

The permissions are shown in the first column, the mix of hyphens and letters, e.g. "drwxr-xr-x". This may look cryptic at first sight but is actually very easy to read.

The first letter shows the type of the file. In case of "subDirectory" we know it's a directory and not a file because of the letter "d" in its permissions.  All other files have a hyphen instead of a letter "d", meaning that they are just regular files. There are other types of files as well but these two are most common.

Then come three groups of three characters: "r", "w", "x" or "-". The first group determines the permissions of the "user" class. For example, in case of "subDirectory" in the screenshot above, its permissions ("drwxr-xr-x") mean that the owner of the file (in this case "shadchnev") has read, write and execute permissions ("drwxr-xr-x").

The second group are the permissions for the "group" class, that is, a group of users (in this case "staff"). For "subDirectory" the group only has the read and execute permissions ("drwxr-xr-x"). The hyphen where "w" could be indicated the lack of "write" permission.

Finally, the last three characters are permissions for the "other" class of users.

In the screenshot above, the longText.txt only had read permission for all users, while someFile has write permission for the group of users, unlike all other files.

#### Changing permissions

So you know how to view and how to read the permissions of a file but how do you change it? The command responsible for it is called "chmod". For example, to give the user a write permission on a file "readme.txt", you'd do

`chmod u+w readme.txt`

Here, "u" stands for user ("g" for group, "o" for others and "a" for all), "+" means that we're adding the permission ("-" means we're removing it) and "w" stands for "write". You can combine several permissions. For example, to remove read and execute permissions from all users:

`chmod a-rx readme.txt`

#### Shebang

We briefly mentioned shebang before but never went into what it actually is. Let's create a file hello.rb with a very simple Ruby program.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381140246212_Screen%20Shot%202013-10-07%20at%2011.03.52.png "cat")

This Ruby file will print "Hello, world" on the screen if executed. Let's run it using ruby.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381140342688_Screen%20Shot%202013-10-07%20at%2011.05.35.png "Hello worlds")

Here we have actually executed ruby and passed "hello.rb" as the argument. The ruby program read the file hello.rb and executed it. However, we normally run various files without having to pass them as arguments to other programs.

For example, you may be already familiar with irb (pronounced eye-are-bee), the Ruby's interactive shell. To invoke it, we can just type irb in the console

`irb`

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381140613000_Screen%20Shot%202013-10-07%20at%2011.10.05.png "irb")

How can we run our little program just like irb by typing its name in the terminal without explicitely invoking ruby? We'll need to do two things: fix the permissions and add a shebang. Let's try running the file first.

Make sure you quit irb if you launched it.

`$ ./hello.rb`
`-bash: ./hello.rb: Permission denied`

(Don't worry about ./ right now, we'll explain why it's necessary soon. It's simply a hint for the terminal that we want to run hello.rb from the current directory. Remember that "." stands for current directory?)

The reason we get permission denied error is that the file doesn't have the "executable" permission by default (list the directory in long format to verify). Let's give the USER (u) permission to EXECUTE (x) the file.

`chmod u+x hello.rb`

Try running the file right now. The permission denied error is now gone but we get another problem.

`$ ./hello.rb`
`./hello.rb: line 1: puts: command not found`

So the terminal (or the shell, to be more precise) complains that it doesn't know what "puts" on line 1 means: command not found. Why is that?

Try to see the situation from the computer's point of view. We asked it to run a program in the file hello.rb but we didn't tell the computer what programming language it was. Was it Ruby? Python? PHP? Something else? The file does have an "rb" extention hinting that it might be Ruby but the computer wouldn't make this assumption. And, even if it's Ruby, we probably have several versions of Ruby installed on the machine: 1.8.6, 1.9.3, 2.0.0, etc. Which one should be used to run our file? The computer needs a specific instruction.

Without a specific instruction it will assume that the file is a "shell script", that is, a set of instructions in the same language that the command line uses. That's why you'll get exactly the same error if try to type `puts 'Hello, world'` in the terminal.

Shebang is the instruction for your computer that tells what program to use to execute your script. It is a combination of a hash and an exclamation mark followed by the path to the interpreter, placed on the very first line of the file.

We want our file to be executed by Ruby, so let's find out where ruby interpreter is first.

`$ which ruby`
`/Users/shadchnev/.rvm/rubies/ruby-2.0.0-p0/bin/ruby`

On my machine, the current version of ruby is located at "/Users/shadchnev/.rvm/rubies/ruby-2.0.0-p0/bin/ruby". Find out where your ruby is and add a shebang to your hello.rb using [Atom](installing_atom.md).

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381141953228_Screen%20Shot%202013-10-07%20at%2011.32.20.png "hello world")

This tells the command line to use this ruby interpreter to execute the file. Now you can type "./hello.rb" and it will print "Hello, world".

`./hello.rb`
`Hello, world!`

What's happening behind the scenes is that the shell (command-line) passes the contents of the file to the interpreter that we specified in the shebang.

However, we've just hardcoded the path to Ruby right in the file. It will work on this computer but not on any other because the path to Ruby will be different. There is a better solution to this problem. Change your shebang to look like this.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381142356445_Screen%20Shot%202013-10-07%20at%2011.38.46.png "shebang")

The "/usr/bin/env ruby" command loads the "environment" (we'll discuss it in a minute) and executes whatever ruby you have on your machine. It may be 1.9.3 on mine and 2.0.0 on yours. This is a much more portable solution than the one we used before.

Remember we mentioned irb as an example of a program that we can run without typing "ruby"? It also has shebang on the first line.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381142632649_Screen%20Shot%202013-10-07%20at%2011.43.41.png "which irb")

Note that the "which irb" command that returns us the path to irb (try it!) is enclosed in backticks (different from apostrophes; located on the left of the "Z" key). This makes the command line "expand" the command, so the real command executed by the computer is

`head /Users/shadchnev/.rvm/rubies/ruby-2.0.0-p247/bin/irb`

The head command that was mentioned above, shows the first few lines of a file. In the screenshot above you can see the shebang on the first line and some Ruby code starting from line two.

#### Superuser mode

Some actions on the computer require administrative (or superuser) privileges. The name of the superuser is "root". If you list the /etc directory where many of the system configuration files are stored, you'll see that all of them are owned by root.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381143662792_Screen%20Shot%202013-10-07%20at%2011.53.45.png "ls -l")

A superuser has all right and permissions to all programs. In other words, the superuser can do any action on the computer. Working as a root is dangerous since entering a wrong command or making a one-character typo can cause significant damage to the system. For example, there's a world of difference (or just one dot) between deleting all files in the current directory

`rm -rf ./*`

and deleting all files on your hard-drive, ignoring read-only flags and avoiding warnings

`rm -rf /*`

Therefore, it's considered bad practice to work as a root on a permanent basis. Instead, you use a normal account with limited privileges (e.g. you can't do "rm -rf /*" and other dangerous things) but switch into a superuser mode only as necessary.

You can execute a command as a superuser by prefixing it with "sudo". For example, if you want to delete a file you haven't got permissions to delete and you know the superuser password, you can

`sudo rm inaccessibleFile`

It will ask you for the password and then the command will be executed with superuser privileges. [It can also be used to make sandwiches](http://xkcd.com/149/).

#### Environment

If you were asked to describe the physical environment you are in, you could tell a few things about where you are (country, city, street, etc.), what temperature and humidity are, what time of the day and what season it is, what language people around you speak etc.

If you are working with the command line, you also operate in an environment. For example, the command-line knows where your home folder is, where to find ruby, what's your username, and many other things. All this information is stored in environmental variables.

Environmental variables (or env vars, for short) describe the current terminal session. You can see them by typing "env".

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381145273378_Screen%20Shot%202013-10-07%20at%2012.27.37.png "env")

Every line on this screen is a key/value pair, e.g.

`HOME=/Users/shadchnev`

The HOME env variable defines where the home directory is for the current user. You can easily find variables responsible for setting the username, language, temporary directory, etc.

Every program you launch on your computer has access to the environment variables. They help the programs to understand what environment they are working in. For example, if you needed to create a temporary file in your Ruby code, you'd read the value of the TMPDIR env variable to find out where the temporary directory is.

You can view any single environment variable by typing "echo $ENV_VAR", e.g.

`$ echo $HOME`
`/Users/shadchnev`

#### A note on echo

One seemingly useless but actually quite useful command available in the terminal is "echo". It just prints whatever text you give it on the screen.

`$ echo "Hello"`
`Hello`

It can be used to view environment variables as we've just seen.

It also can be used to save short strings to a file. Let's say you want to create a file with text "Hello, world".

`echo "Hello, world" > hello.txt`

This command will turn out to be useful on more than one occasion later.

#### PATH

One of the most important environment variables is PATH, so let's discuss it in detail. PATH is a colon-separated list of directories where the shell will be looking for the programs you ask it to run. On my computer it looks like this.

`$ echo $PATH
/Users/shadchnev/.rvm/gems/ruby-2.0.0-p247/bin:/Users/shadchnev/.rvm/gems/ruby-2.0.0-p247@global/bin:/Users/shadchnev/.rvm/rubies/ruby-2.0.0-p247/bin:/Users/shadchnev/.rvm/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin`

This is a list of paths, separated by colons. When you type a command without specifying its path, e.g. "ruby", the shell looks through all these directories until it finds this file and executes it. So, when you type "ls", the shell will be examining the following paths in order until it finds a file that exists.

`/Users/shadchnev/.rvm/gems/ruby-2.0.0-p247/bin/ls`
`/Users/shadchnev/.rvm/gems/ruby-2.0.0-p247@global/bin/ls`
`/Users/shadchnev/.rvm/rubies/ruby-2.0.0-p247/bin/ls`
`/Users/shadchnev/.rvm/bin/ls`
`/usr/bin/ls`
`/bin/ls`
`/usr/sbin/ls`
`/sbin/ls`
`/usr/local/bin/ls`

On my system, "ls" will be found in "/bin/ls".

Remember when we had to type "./hello.rb" to execute the file, instead of just "hello.rb"? This is because if we hadn't explicitely specified that the program was in the current directory, the shell would look in all PATH directories and wouldn't find it there. Every program that you can run from your command line without specifying where they are (ls, chmod, date, pwd, etc) are somewhere on the PATH.

You may have tried switching ruby versions on your machine using rvm.  If not, you soon will be :-) How does it work? When you type

`rvm use 1.9.3`

rvm updates the PATH variable to include the folders relevant to the ruby version that you need. Then, when you type "ruby", the shell already knows where to look.

If you have installed some software but you can't run it (command not found error), double check that the PATH variable is set correctly.

Setting environment variables

So far we've seen how to read environment variables. We can also set them. Try

`export SEASON=winter`

You've just created a new environment variable called SEASON. You can read its value back.

`echo $SEASON`

What if we wanted to modify PATH? Let's add one more directory at the end of PATH:

`export PATH=$PATH:/Users/shadchnev`

This adds my home directory to the end of the list of paths in PATH.

Why would we want to modify environmental variables? One of the common use cases is storing sensitive data, e.g. passwords.

Let's say you're writing an open source project that uses photos from Facebook. Your code will need to use a secret key that will give you access to Facebook. This key is secret and you shouldn't share it with anyone. However, you want to share your open source code on Github. How should you do it?

Put your secret key in an environment variable and then read it from your code when you need it. For example:

`export SECRET_KEY=12345abcde`

Then, in your Ruby code, read the value:

`secret_key = ENV['SECRET_KEY']`

This way you'll be able to share your code with anyone without compromising your keys.

#### Profile files

The environment variables don't last for long. After you set them, they only stay in the environment until the end of the current shell session. However, you normally want them being available in all new shell sessions as well. Profile files are often used to achieve this.

Let's create (or re-create if it already exists) the env variable SEASON.

`export SEASON=winter`

Verify that it exists.

`$ echo $SEASON`
`winter`

Now open another terminal window and try to see if the variable exist. It shouldn't: it only exists in the shell where it was originally created. Every variable should be recreated every time a new terminal session starts.

Every time a new shell session starts, several files are executed automatically on load. They are used, among other things, to configure the environment. One of these files is called .bash_profile (note the dot at the beginning). It is located in the home directory.

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381154289375_Screen%20Shot%202013-10-07%20at%2014.57.59.png ".bash_profile")

If you have RVM installed (as you should), there will be some code related to loading RVM into the shell. This code makes RVM available for you to use in every shell.

We can also use the same file to create "permanent" env vars. Let's put our SEASON variable into the file.

`echo "export SEASON=winter" >> ~/.bash_profile`

(Double angle bracket means append, while single angle bracket means overwrite)

Now our .bash_profile file looks like this:

`[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*
export SEASON=winter`

Now open a new shell window and verify that the variable exists. If you've done everything correctly, it will.

#### Processes

Every program running on the system is composed of at least one "process". A process is simply some code that is being executed (that hasn't finished yet). Simple programs usually launch just one process but sometimes a program can launch several processes in parallel.

You can see what processes you launched by using the "ps" command.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381159022741_Screen%20Shot%202013-10-07%20at%2016.15.05.png "ps")

I have quite a few terminal windows open in parallel, so I have a "bash" process for every one of them. If you use the "x" flag, you'll see all processes running on your computer.

`ps x`

By redirecting the output to grep you can filter out the processes you need, e.g. if you want to only see bash processes running on the system:

`ps x | grep bash`

How could you use "wc" command that we discussed earlier to count their number?

#### vim

We've resorted to using [Atom](installing_atom.md) earlier but we won't always have the luxury of using graphical user interface. When connecting to a remote system, a shell (text-only command-line) will be the only interface you'll often have. Even worse, you may not have user-friendly text-based editors (e.g. nano) installed when you need to make a quick change. However, you'll need to look hard to find a system that doesn't have vi or vim (vi iMproved) installed.

This editor may seem very unfriendly at first, but if it were really unusable it wouldn't be so popular among developers and system administrators (why do they use vi?). From a practical perspective, it's worth knowing the basics because that's the editor you can always rely on, on any unix-based system.

To create a new file or open an existing file, just pass it as an argument.

`vi myFile`

You'll see the empty file first.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381161102740_Screen%20Shot%202013-10-07%20at%2016.51.35.png "vim")

You can't type anything yet, though, because the editor is not waiting for your text input. By default it will be in a "command" mode when vi waits for a command and not an "insert" mode when it's expecting you to enter text. Right now you could give it one of many commands:

* i – insert text before cursor
* o – open a new line after the current one
* dd – delete current line
and dozens of others

Let's suppose we want to save a file with the text "Hello, world" inside. Press "i" once. The editor will switch into the insert mode:

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381161468370_Screen%20Shot%202013-10-07%20at%2016.57.41.png "insert")

Now whatever you type will be actually entered as text. Type "Hello, world". How do you save it now? Whatever you press now will be taken not as a command (save, exit, etc) but as text. To get back to the command mode press ESC. Now you're back in the command-mode.

![alt text](https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381161644651_Screen%20Shot%202013-10-07%20at%2017.00.35.png "vim writing")

Now we can tell vi to save the file. Press colon (:) and then w ("w" stands for "write").
 ![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381161741131_Screen%20Shot%202013-10-07%20at%2017.01.57.png "vim writing")

 After you press Enter, the file will be written and you'll see the corresponding message.

![alt text]( https://dchtm6r471mui.cloudfront.net/hackpad.com_o6W2ogQY8Xc_p.52567_1381161787432_Screen%20Shot%202013-10-07%20at%2017.02.59.png "Vim written")

Now we need to quit the editor. Type :q followed by Enter. (If you needed to quit without saving changes, you'd need to do :q!).

This is the absolute minimum you need to know to make a basic edit using vi. Print a [cheat sheet](http://www.lagmonster.org/docs/vi.html) and practice using vi on a few files.

#### Exiting the shell

Finally, to exit the shell, just type "exit" :)
