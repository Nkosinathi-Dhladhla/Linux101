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

# Absolute and Relative paths
- A path identifies the location of a file or directory

## Absolute 
- Absolute paths always start at the root of the file system and ignore your current directory
- E.g: ls /home/bob/files/notes.txt

## Relative path
- A relative path starts from your current working directory. It changes depending on where you are
- E.g: If your current directory is /home/nathi then cd Documents is equivalent to cd /home/nathi/Documents
- you can also use (.) for relative E.g:
- Suppose you're in: /home/nathi/Documents/CTF
. (current directory) ./flag.txt means: /home/nathi/Documents/CTF/flag.txt
If there's an executable called exploit: ./exploit means "run the exploit program that's in my current directory"
- ..(parent directory)
cd .. takes you to /home/nathi/Documents
cat ../notes.txt means go up one directory, then open notes.txt
So from: /home/nathi/Documents/CTF it becomes /home/nathi/Documents/notes.txt
- Another example: ../../ 
cd ../../ From: /home/nathi/Documents/CTF
it takes you to: /home/nathi

## When to use absolute and relative paths 
- If you need a path that is valid from anywhere on the file system use an absolute path
- Relative paths are shorter and easier to use. Using a relative path assumes that you're in the same directory structure

# Working with Files and Directories 
- To check the last modified timestamp on the text file use the following command (Please note that note.txt is just an example): ls -l notes.txt
- To update the modification time use this command: touch notes.txt then execute the previous command again (ls -l notes.txt)
- If you want to make a copy of a text file use the following command: cp notes.txt notes-copy.txt
- To specify the destination of the source use the following command: mv notes-copy.txt ./backup
- If you want to delete the file use this command: rm backup/notes-copy.txt
- use the mkdir command to create a new directory: mkdir project
- Use ls to check the newly created directory
- If you decide to remove the directory use the following command: rmdir project
- The rmdir command doesnt work if the directory has files or other directories in it. It only works if the directory is empty
- If you want to delete an empty directory with files then use the rm command used to delete files: rm -rf non-empty-dir/
- If you need to rename a directory you can use the same mv command used for the file: mv project project01

# Spaces in Paths and Filenames
- Do not use spaces when naming files. Rather use underscores
- If you're finding yourself in a situation where you have to use filenames that have spaces in a command you can bypass this command by doing the following:
  - you can escape the space using a slash like this: (initially the file name is file name.txt) cd file\ name.txt
  - You can also place the entire name in quotes: ls 'file name.txt'
 
# File and Path Expansion
- the asterisk can be used to view files that start with a specific string.
- eg: ls file*.txt will display every file character
- If you want a file with specific characters you can use the question mark
- eg: ls file?.txt
- if you want to match a file with a specific number or letter you can do the following
- eg: ls file[123] or ls file[a-z]

# Even More Looking at Text Files
- sometimes we want to view the first few lines of a text file. you can use the head command for this
- eg: head wordlist.txt
- or head -n 5 wordlist.txt
- or head -5 wordlist.txt
- or tail wordlist.txt, or tail -n 5 wordlist.txt, or tail -5 wordlist.txt
- The diff command is used to find the difference between two files
- eg: diff file1.txt file2.txt

# Hard and Soft Filesystem Links
- A hard link points to the physical location of the file on storage
- eg: ln hello.txt hello-hard-link.txt
- Soft link:
- eg: ln -s ./hello.txt hello-soft-link.txt
- ls -l hello*
  
