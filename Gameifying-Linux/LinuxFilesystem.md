## The Filesystem



### Directories


In Linux, files are referred to as _directories_. In a typical desktop environment, you can see the files and directories that you’re interacting with on the screen. In a command-line environment like the Linux shell, these files and directories are still present, but are not visible to the user. This means that while working in the shell you will have to remember which directory you are working in. 

This may prove to be difficult for new command-line users, but once you are familiar with your system, you’ll find that you can navigate through the file system faster than you could on a typical system. 

You can use commands like <code>pwd</code> (for “print working directory”) and <code>cd</code> (for “change directory”) to keep track of where you are and change directories.



### The File Tree



![alt_text](filetree_diagram.PNG "image_tooltip")


You can think of the Linux filesystem as a tree, where subdirectories branch from their parent directories, and the _root_ directory is denoted with a “/”.

Directories are referred to with a series of names and slashes called the _path_, so for instance, the path: 


```
/one/two/three/four
```

refers to the root directory “/”, which contains a directory called _one_, which contains a directory called _two_, which contains a directory called _three_, which itself contains a file called _four_. Much like other tree-like structures, directories in the Linux filesystem have child/parent relationships, with _parent directories_ being called just that, and child directories being referred to as _subdirectories_. This means that a given directory could have any number of subdirectories, but each directory will only have one parent directory.



### System Directories

Within the root directory, there are many subdirectories that contain files essential for the function of the operating system. Some, but not all of these directories will be listed here for your convenience.



* _/bin_: The _bin _folder is where the operating system stores its binaries. These are executable files that are essential to the programs running on your system
* _/etc_: The _etc _folder is where many configuration files are kept
* _/home_: This is where the home directories for the different users are stored, not that the root user does not have a home directory
* _/var_: Files stored in _var_ are temporary, they are a place for the operating system to create, edit, and delete information in runtime. 

This list is by no means exhaustive, but it is a good place to start for the curious. Do some research on your machine and see what else you can find!



### Absolute and Relative Paths

It is also important to note that the Linux shell makes use of what are referred to as _absolute_ and _relative_ paths. An absolute path is one that begins from the root directory. For example, in the image above, there are two directories named “_bin._” One has an absolute path of _/bin_ and the other has an absolute path of _/usr/bin_. Simply referring to the “_bin_” directory leaves an incomplete picture, more information is needed. A relative path, on the other hand, is any path that does not begin with the root directory “/”.

In order to properly interpret a relative path, you must know “where” in the filesystem you are currently working. This is know as your _current working directory_. Every shell has a current working directory, and running commands executes them in relation to that directory.

For instance, assume your current working directory is “_/usr_”, referring to “_bin_” in this directory will actually be referring to “_/usr/bin_”. This is the general case, for another example, assume your current working directory is “/_one/two/three/four_” and you refer to “_a/b/c_”. This will imply an absolute path of “/_one/two/three/a/b/c_”

There are also two special relative paths: . (a single period) and .. (two periods in a row). A single period refers to your current working directory, and two periods refers to your parent directory (one step above). If your current working directory is ‘_/one/two/three_’, then .. refers to ‘_/one/two'_.



### Changing Working Directory

Moving from one directory to another is simple, and only requires you to execute the <code>cd</code> command:


```
-> cd /usr/local/bin
```


The “_cd_” command can accept both absolute and relative paths for its argument:


```
-> cd d         ## enters the subdirectory d
-> cd ../mydir	## go up to the parent directory, then into the directory mydir
-> cd ~         ##takes you back to the logged user's home directory
```
