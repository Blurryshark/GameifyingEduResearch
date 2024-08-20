# Command information ( Specific to practice challenges )
## File operations 



### Ls


```
ls [options] [files]
```

The _ls_ command (pronounced as it is spelled, _ell ess_) lists attributes of files and directories. You can list files in your current working directory:


```
-> ls
```


In given directories:


```
->ls mydir mydir2 mydir3
```


Or individually:


```
-> ls myfile myfile2 myfile3
```


There are a few options for _ls _that will be used very commonly. Do some research and find out what they are!



### Touch


```
touch newfile
```


Touch will create a new empty file with the name specified in the argument. It should be noted that in Linux, every file is treated as a simple text file unless an extension is specified. Executing: 


```
-> touch myScript
```


will create an empty text file called _myScript_, while executing: 


```
-> touch myScript.py
```


will create a new empty python script that can be later executed. 



### Cp


```
cp [options] files (file OR directory)
```


The cp command (for “copy”) copies one or more files into a different directory. Lets say you wanted to copy a file into _mydirectory_:


```
-> cp myfile myfile2 myfile3 mydirectory
```


**Useful Options**


    -p    Copy the files contents in addition to its permissions, timestamps, and it’s owner and group (whereas they would normally be owned by the copier, timestamped now, and with default permissions)

    -i 	Interractive mode, will ask before overwriting destination files


    -f 	Force the copy. If a destination file already exists, it will be overwritten unconditionally



### Mv


```
mv [options] source target
```


The _mv_ (for “move”) command will move a file to another directory:


```
-> mv myfile destination-directory
```


Interestingly, this can also be used to rename a file by moving the file into a newly named file in the same directory:


```
-> mv fileWithAName ./fileWithAnotherName
```


**Usefult Options**


    -i	Interactive mode. Ask before overwriting destination files.


    -f	Force a move. If a destination file already exists, it will be overwritten unconditionally



### Rm


```
rm [options] files OR directories
```


The rm (for “remove”) command can delete files:


```
->rm deleteme deleteme2
```


or recrusively delete directories:


```
-> rm -r myDirectory
```


**Useful Options**


    -i	Interactive mode. Will ask before deleting each file


    -f	Force the deletion of a file or directory, this ignores any errors or warnings


    -r	Recursively remove a directory and its contents. Use with caution, especially when combined with _-f_. This could wipe all the files on your computer.

A common joke you will find on online message boards will be pranksters who respond to those in need of technical assistance by informing them their problem will be fixed by ‘removing the French Language Pack’ from their machine. This involves executing: 


```
-> rm -fr /
```


As you might expect, this has the effect of recursively and forcibly removing the root folder, destroying the entire operating system installation. 


## File Viewing



### cat 

`cat [options] [files]`

cat is by far the simplest way to view the contents of a file. It will simply print the contents of the file to standard output (the terminal). Using _cat _with multiple files for arguments will concatenate the file contents (hence the name): 


```
-> cat myfile
```


Large files will scroll off your screen. In most terminals you have the option to scroll, but this is not always the case. _cat_ is also very useful for sending file contents into a shell pipeline, an advanced technique that will not be covered here

**Useful Options **


    -T	Print tabs as ^I


    -E	Print newlines as $


    -v	Print other nonprint characters in a human-readable format


    -n	Prepend line numbers to every line


    -b	Prepend line number to nonblank lines


    -s 	Squeeze each sequence of blank lines into a single blank line



### Less


```
less [options] [files] 
```


Use _less _to view text one “page” at a time (i.e., one window or screenful at a time):


```
-> less myLongFile
```


This is very useful for viewing large text files that might otherwise take up the entire screen.

**Useful Options**


    -c	Clear the screen before displaying the next page. This avoids scrolling and may be more comfortable on the eyes


    -m  Print a more verbose prompt, displaying the percentage of the file displayed so far


    -N	Display line numbers


    -r	Display control characters literally; normally `less `converts them to a human-readable format

### grep
### wc
### piping

## File Editing
### vim 
```
vim filename
```
vim is one of many file editors that can be installed in Linux, it is an enhanced version of a classic Linux text editor named vi.

When opening a file with *vim*, you will not immediately be able to add or remove text. To add or remove text from the document, you must enter `insert` mode by pressing the `i` key. 

When in `insert` mode, you will not be able to exit the editor or save your work. To do so, you must first exit `insert` mode by using the `escape` key. In order to save and quit your work on the file you are editing, you must enter `:wq`. This tells *vim* to 'write' your changes and then quit the program.

*vim* also has features that you will find in many IDEs available through a graphical user interface. These features will be activated depending on the kinds of files you open. For instance, if you open a file with an extension related to any programming language (java, C, C++, etc), you will notice that *vim* will highlight any open brackets and curly braces, as well as highlighting reserved words and variable names.

These are just the basics of using *vim*, and there are many more command line-based text editors besides, the best way to get familiar with *vim* is to practice using it. 

```
-> vimtutor
```
will start an interactive tutorial on how to use it.

## Directory Traversal and Manipulation



### Cd


```
cd [directory]
```


The cd (for “change directory”) command sets your current working directory.



### Pwd


```
pwd
```


The _pwd _command will print the absolute path of your current working directory.



### Mkdir


```
mkdir [options] directories
```


mkdir (“for Make Directory”) creates one or more directories.

**Useful Options**

```
    -p	Given a directory path, will create any necessary parent directories automatically. The command:

        ->mkdir -p one/two/three

    creates one and one/two and one/two/three if they don’t already exist.
```

### Rmdir

```
rmdir [options] directories
```

The _rmdir_ (remove directory) command deletes one or more empty directories you name: 
```
-> mkdir /tmp/junk		## makes a directory
-> rmdir /tmp/junk      ## deletes that directory
```

rmdir only works on empty directories. If you want to delete a non-empty directory and it’s contents, then you must use _rm -r_

## Searching and Finding

### Grep
```
grep [options] pattern [files]
```
The _grep_ command's premise is simple. Given one or more files, print the lines in that file that match the supplied pattern. Given a file called *randomText* that contains these lines: 
```
The quick brown fox jumped over the lazy dogs!
My very eager mother just served us nine pancakes. 
Film at eleven.
```
we can search for all the lines containing "pancake". We get: 
```
-> grep pancake randomText
My very eager mother just served us nine pancakes
```
**Useful Options**
```
-v  Print only lines that do not match the regular expression

-c  Print only a count of matching lines

-n  In front of each line of matching output, print its original line number
```

