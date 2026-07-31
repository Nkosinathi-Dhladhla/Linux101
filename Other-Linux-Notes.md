# Introduction to the command line
whoami - returns the name of the user 
hostname - returns the name of the current host 
pwd - short for print work directory. This tells you which folder you are currently inside
ls - lists the contents of a directory
cd - short for change directory. E.G: cd files. This is used to change the directory the user is currently in

# Getting help on the command line
There are many ways to get help on the command line. One of the ways to get help is by using man which is short for manual. Here are the different ways to get help: 
man - eg: man ls. This will display a manual on how to use this specific command. To get out of the man page, simply press Q.
Info - eg: info ls
ls  help - this is another way to get help

# Looking at text files; More or Less:
Type ls to view a list of files. Choose a file such as wordlist.txt by typing: more wordlist.txt
you can also type less wordlist.txt. More and less are used to view the contents of a specific file. More displays a basic view of the page, less displays a more powerful page viewer that can be controlled. 

# Another way to look at contents of a file (cat):
cat is used to display the contents of the file directly in the terminal
eg: cat file.txt
- Calling cat without a file name will just echo what youre typing. E.g: cat
                                                                        Hello World
                                                                        Hello World
                                                                        Goodbye
                                                                        Goodbye
  - Use ctrl+v to exit out of a cat command
