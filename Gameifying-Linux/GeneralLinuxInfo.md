# Basic Linux Stuff ( General information )

##  What is a Shell

The primary way you or any other user will interact with the Linux operating system is through the graphical user interface complete with icons and menus. This user interface is useful for some simple tasks, like web browsing and reading emails, but the true power of Linux lies in use of the _shell_. 

The shell exists beneath the graphical user interface, and exists as a command-line interface, but how can the user interact with the shell from the GUI? The good news is that despite many graphics interfaces existing for Linux such ash GNOME, KDE, and Cinnamon, they all come with a preconfigured program called a _terminal_. The terminal program will be called by different names depending on the Linux distribution (Terminal, Konsole, etc.), but they all allow the user to issue commands to and read output from the shell.  

![shell_diagram.](shell_diagram.PNG)

## Shell Prompts


 Commands can only be executed if the Linux shell if it is ready to accept them. The shell will notify you it is ready by displaying a _prompt_. The prompt may be a symbol such as a dollar sign:



<code>$</code>

 or a complex string that displays information about who is signed in and on what machine:


<code>liamcristescu@Desperado:~$</code>

 The styles of prompt are myriad, and will vary depending on which version of Linux is installed on your machine. In these instructions, this symbol <code>-></code> will be used to indicate a shell prompt and should not be typed as part of a command.



## What is a command

A Linux command usually consists of the invocation of a program that is installed on your machine, typically followed by options and arguments. You can think of this as invoking a Java or C++ function that is defined somewhere else in your program or a library. It will look something like this: 


```
-> wc -l myfile
```


The program name (wc, short for “word count”) refers to a program installed elsewhere on the disk that will be run by the shell. Here, Word Count has been invoked with the `-l` option, telling the program to count _lines_ instead of words. Additionally, `myfile` has been supplied as an argument, telling _word count_ to count the number of words (or, in this case, lines) in `myfile`.



## How commands work

So what happens between executing a shell command and seeing the output displayed on your screen? The answer is: “it depends.” Depending on the command being executed, the shell will take different actions. There are three cases:



1. The executed command is a _shell builtin_: The function of this command is built into the shell, and thus these will be executed the fastest and with the least amount of computational overhead. The `cd` command is the most common example of this. 
2. The executed command is an installed program: The function of this command is defined in a binary executable installed on the machine. The Linux operating system comes with many executable commands pre-installed, and many more can be added by the user. The `ls` command is one such executable. 
3. The command is an _alias_: An alias a kind of ‘shortcut’ to a different command in the shell that can be created by the user. Depending on which Linux distribution you have installed, there may be pre-configured aliases. For instance, Ubuntu will have `ll` pre configured as a shortcut for `ls -l`.

###  Command Line Practice

Here are some basic commands you can execute to get used to the feel:
```
-> whoami
```
will ask the shell to print the user that is currently logged in.
```
-> cal aug 2024
```
will print the calendar of August 2024 to the command line.


```
-> wget http://linuxpocketguide.com/sample.pdf
```


Download a pdf from the internet into your current directory without a web browser.


```
-> ls /bin
```


will print the contents of the binaries folder, where many commands and programs are stored.


```
-> df -h /
```


Shows how much space is used on a partition of your hard disk


```
-> top -d1
```


Will allow you to watch the processes running on your machine (type “q” to quit this program)


```
-> last -1 $USER
```


Shows how long you’ve been logged in.


```
-> whois csumb.edu | less
```


Will show who owns the domain name _csumb.edu_ (press the spacebar to move forward page by page, and type “q” to quit)

An important reminder, Linux shells are case-sensitive! Getting the case wrong may execute the wrong command, or no command at all!


```
-> Ls /bin
Ls: command not found
```


Because we have executed the _ls_ command with and incorrect capitalization, the shell has not recognized the command, and informed us that the action could not be executed.



## Command options and how to read them

A note on how commands will be described in these materials, and the difference between an _option_ and an _argument._

Nearly every command you issue to the terminal will have one or more arguments supplied with it. For instance, the *ls* command requires an argument in order to list the contents of the a given directory (note that in this example, if no argument is supplied, *ls* will list the contents of the current working directory).
```
ls
```
Options, on the other hand, are functions you can activate to change how the command executes. For instance, the *-a* option will cause *ls* to list **ALL** the content of the directory supplied in the argument, including hidden files. 
```
ls -a
```

## man & -h/–help [MOVE TO UTILITIES]

Although we will cover many commands and many more options for these commands here, you may yet need more information not provided within the materials for this section. Luckily, there are a few ways Linux has accounted for the average user’s lack of encyclopedic knowledge on every command.

Many commands have a help option! This option is usually “-h” or “--help.” Try this now with the “ls” command: 


```
-> ls –help
```


The `man` command is also an option, this displays an online manual page, known as a _manpage_ for a given program. Try executing the `man` command with `ls` as the argument like below: 


```
-> man ls
```



## Users and Superusers 

Linux, being a multi-user operating system, is designed so that multiple users can work on a single computer at the same time. This system is designed such that each user owns their own private part of the system in which they can do their work, this means that users will only be able to access files and directories that they have created. 

There is, however, a special user known as the _superuser_ who has the ability to access, modify, or delete anything on the system, including files and directories that they themselves have not created. This user is typically referred to as the _root user_.

Root user permissions are not enabled by default in the shell, and must be activated by prepending _sudo_ to certain commands. For example, executing this command:

```
-> touch /bin/newFile
touch: cannot touch '/bin/newFile': permission denied
```


will result in the shell denying us permission, this is because _/bin_ is a protected folder and is not accessible to normal users. However, executing: 


```
-> sudo touch /bin/newFile
```


will prompt the user to enter root’s password in order to temporarily be given superuser permissions, allowing the user to modify the protected folder. 

**_WARNING:_** The use of the sudo command is very powerful, and should only be used with extreme caution, as it gives the user the power to delete essential files, including those that are necessary to the functioning of the operating system. Some actions cannot be undone!



## Command history

Doing any kind of work on the Linux command line can sometimes involve executing the same command repeatedly, think of having to continually recompile source code after making changes or having to re-execute a failed download. 

These are situations you will undoubtedly encounter in your time on the command line. While retyping the same commands multiple times will get the job done, true power on the command line comes from finding ways to accomplish tasks with increased efficiency through shortcuts.

One such shortcut is the **up and down arrow keys**, this will allow you to browse through commands you have recently executed. From a blank prompt. Pressing the up key once will fill the prompt with your previous command, pressing up again will show the command before that, and so on.

You can also execute this command: 


```
-> history | tac | less
```


this command will print the file that stores your command history page by page (press space bar to print a new page and “q” to quit). This can be preferable to seeing the command entries displayed one-by-one on the prompt.



## Auto-complete Commands

Another helpful shortcut that will help you in your command line journey is the use of the TAB key. Linux is fairly effective at anticipating what you are going to type next, if you are using a particularly wordy option for a command or navigating to a directory, using the TAB key will let the Shell know to fill in the best option based on what you’re trying to do. 

For instance, typing:


```
-> cd ~/Down
```


before hitting TAB will let the Shell know that it should automatically complete this command. Depending on the layout of your home directory, your command will likely be completed with: 


```
-> cd ~/Downloads
```


This can cut down significantly on typing time. It is also an effective way to see what options are available to you. For example, try typing:


```
-> cd ~/Do 
```


before hitting TAB. Notice that nothing happens, this is because there are two possible options that this command could be auto-completed to. Hit the TAB key again to have these options listed out to you. Note that this works while typing all arguments as well as options for commands.



## Killing Programs

There will be times when you want to stop a command from executing before it has finished. This may happen when a program hangs or when you open a very large file. To do this type CTRL + C. Note that this can cause programs not to ‘clean up’ properly when they close, leaving your shell without a prompt





