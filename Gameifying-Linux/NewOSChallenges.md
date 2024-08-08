# OS Challenges

apt | wget > tar > C compiler > grep + 

## Challenge 1
Intent: Students will download  a text file using *wget*, and then use *grep* and *wc* to find the occurences of a word or phrase in the file

### Step 1
Students will download a text file from the web using 
```
wget https://courses.cs.washington.edu/courses/cse163/20wi/files/lectures/L04/bee-movie.txt
```
### Step 2
Students will determine the amount of times the word "bee" appears in the downloaded file using 
```
grep bee bee-movie.txt | wc -l
```
### ALTERNATE Step 2
Students will take all lines containing the word "bee" and put them in a text file to be counted later
```
grep bee bee-movie.txt > beeFile.txt
```
### ALTERNATE Step 3
Students will count the lines in this file by executing 
```
wc -l beeFile.txt
```
## Challenge 2
Intent: Students will download the C compiler using *apt*, then use *wget* to download a file containing C source code. Students will finally have to use *vim* in order to make changes to the code, compile the code, and then finally execute it.

### Step 1
Students will update the package registry with 
```
sudo apt update
```
### Step 2
Students will download the C compiler with 
```
sudo apt install gcc
```
### Step 3
Students will now download the provided source code by executing 
```
wget [URL]/source.c
```
### Step 3
Students will make the necessary changes to the file by executing 
```
vim source.c
```
### Step 4
Students will compile their new source code with 
```
gcc source.c -o compiled
```
### Step 5
Students will finally execute their new binary file with
```
./compiled
```

## Challenge 3
Intent: Students will download a compressed directory and submit information about the directory.