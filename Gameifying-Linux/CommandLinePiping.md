# Command Line Piping
## What is Piping? 
One of the most powerful functions a user can invoke on the command line is the *pipe*. 

The Pipe function is unique in that it must be invoked between two different commands. For example,
```
tail file.txt | grep 'pattern'
```
is how you would pipe the *tail* and *grep* functions. As you can see, the syntax is rather simple. You simply need to use the `|` character between the two commands you would like to pipe. 

But what does piping actually do? In the example above, the output of the *tail* command is used as the input for the *grep* command. You can envision this as a kind of 'redirection,' where the result of the first command is used as the argument for the second command, instead of being printed to standard output. 

Where piping gets very powerful is when it is used in sequence with other pipes.
```
grep GET networkcapture.txt | uniq | grep user | wc -l
```
In this example, three pipes are used. The initial command, *grep* is piped into *uniq*, which is piped into another *grep*, which is then piped into a final *wc* command. It is not important to know what these specific commands are doing, but instead recognize that a task which might take one user several commands to accomplish can be accomplished swiftly by another user with pipes. 