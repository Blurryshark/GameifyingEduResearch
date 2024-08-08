# Practice Challenges
## *man* Challenges
### 1. *ls*
Prompt: Write the command that would be used to open the manpage for *ls*

Deliverable: `man ls`

Prompt: Which *ls* option outputs in a long listed format?

Deliverable: `-l`

### 2. *touch*
Prompt: Write the command that would be used to open the man page for *touch*

Deliverable: `man touch`

Prompt: Which option will cause *touch* to change only the access time of a file

Deliverable: `-a`

### 3. *cp*
Prompt: Write the command that would be used to open the man page for *cp*

Deliverable: `man cp`

Prompt: Which option creates hard links instead of copying files

Deliverable: `-l`

### 4. *mv*
Prompt: Write the command that would be used to open the man page for *mv*

Deliverable: `man mv`

Prompt: Write the command that makes mv explain what is happening

Deliverable: `-v`

## *mv* Challenges
### 1.
Prompt: Write the command to move a file named *myfile* from your downloads to your documents folder (use RELATIVE paths).

Deliverable: `mv Downloads/myfile Documents`

### 2. 
Prompt: Write the command you would use to take a file in your downloads folder name *myfile* and rename it *myNewFile* (use RELATIVE paths).

Deliverable: `mv Downloads/myfile Downloads/myNewFile`

## *ls* Challenges
All should be completed from the HOME directory (all RELATIVE paths should be 'from' the home directory)

### 1.
Prompt: Write the command you would use to see your Downloads directory

Deliverable: `ls Downloads`

### 2. 
Prompt: Write the command you would use to see the root (/) directory

Deliverable: `ls /`

### 3. 
Prompt: Write the command you would use to see the */etc* directory

Deliverable: `ls ../../etc`

## *sudo* challenges
### 1. 
Prompt: Which sudo option changes the logged user of the shell into ROOT? 

Deliverable: `-s`

### 2. 
Prompt: What is the new shell prompt once the ROOT user is logged in? 

Deliverable: `root@machine_name:/home/user`

## *touch* challenges
### 1. 
Prompt: Enter the command you would execute to create file in your current directory named 'myNewFile'

Deliverable: `touch myNewFile`

### 2. 
Prompt: Enter the command you would execute to create file in your current directory's parent directory named 'myNewFile'

Deliverable: `touch ../myNewFile`

## *cp* challeneges
### 1. 
Prompt: Enter the command you would use to copy the contents of a file called 'myFile' to a file called 'myNewFile'

Deliverable: `cp myFile myNewFile`

### 2. 
Prompt: Enter the command you would use to copy the contents of a file called 'myFile' to a file in the parent directory called 'myNewFile.' Use the option that will copy the file contents in addition to its permissions, timestamps, and owner group

Deliverable: `cp -p myFile ../myNewFile`

## *mv* challenges
### 1. 
Prompt: Enter the command you would use to rename a file named 'myFile' to a file called 'myNewFile'

Deliverable: `mv myFile myNewFile`

### 2. 
Prompt: Enter the command you would use to move a file named 'myFile' up into the parent directory and down into another child directory called 'copiedFiles'

Deliverable: `mv myfile ../copiedFiles`

## *rm* challenges
### 1. 
Prompt: Enter the command you would use to remove a file named 'fileToDelete' from the current directory

Deliverable: `rm fileToDelete`

### 2. 
Prompt: Enter the command you would use to remove a file named 'fileToDelete' from the parent directory

Deliverable: `rm ../fileToDelete`

### 3. 
Prompt: Enter the command you would use to recrusively remove a directory named 'directoryToDelete' from the current working directory. You have to use the 'force' option

Deliverable: `rm -rf directoryToDelete`

## *cat* or *less* challenges
### 1a. 
Prompt: Enter the command you would use to print the entire file named 'fileToPrint' that is in a subdirectory called 'subdirectory'

Deliverable: `cat subdirectory/fileToPrint`

### 1b. 
Prompt: Enter the command you would use to print the same file page by page

Deliverable: `less subdirectory/fileToPrint`

### 2a. 
Prompt: Enter the command you would use to print the entire file named 'fileToPrint' that is two parent directories up from the current working directory

Deliverable: `cat ../../fileToPrint`

### 2b. 
Prompt: Enter the command you would use to print the same file page by page

Deliverable: `less ../../fileToPrint`

## *cd* challenges
### 1. 
Prompt: Enter the command you would use to change directories to the HOME directory

Deliverable: `cd OR cd $HOME`

### 2. 
Prompt: Enter the command you would use to enter the directory 'targetDirectory' that is two parent directories up from the current working directory

Deliverable: `cd ../../targetDirectory`

### 3. 
Prompt: Enter the command you would use to enter the directory 'four' that is inside the directory 'three' that is inside the directory 'two' that is inside the direcctory 'one'

Deliverable: `cd one/two/three/four`

## *mkdir* challenges
### 1. 
Prompt: Enter the command to create the new directory 'newDirectory'

Deliverable: `mkdir newDirectory`

### 2. 
Prompt: Enter the command to create the new directory 'three' inside the new directory 'two' inside the new directory 'one'

Deliverable: `mkdir -p one/two/three`

## *rmdir* challenges
### 1. 
Prompt: Enter the command to remove the empty directory 'dirToRemove' from the current working directory

Deliverable: `rmdir dirToRemove`

### 2. 
Prompt: Enter the command to remove the empty directory 'dirToRemove' from the parent directory

Deliverable: `rmdir ../dirToRemove`

### 3. 
Prompt: Enter the command to remove the empty directory 'dirToRemove' from the subdirectory 'subdirectory'

Deliverable: `rmdir subdirectory/dirToRemove`

## File Operations
### touch
### mv
### cp
### mkdir
### rmdir
## Utility
### sudo
### man
### grep
### find
~~

submit bash history file?

### File/Directory creation and moving (10 pts)
prompt: create a file named submission.txt in your home directory before moving it to the subdirectory submissionDirectory

execute the command `history -a` to save your bash history, and submit the contents of ~/.bash_history to complete this challenge

~~

### TODO Challenges
wget

apt

C compiler

BASH scripts (running and writing)

grep

vim


## Creating and moving files