# Learn command line

Please follow and complete the free online [Command Line Crash Course
tutorial](https://web.archive.org/web/20160708171659/http://cli.learncodethehardway.org/book/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. Each "chapter" focuses on a command. Type the commands you see in the _Do This_ section, and read the _You Learned This_ section. Move on to the next chapter. You should be able to go through these in a couple of hours.

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > - `pwd`: show current working directory path  
> > - `hostname`: show the name of your computer
> > - `mkdir [directory]`: create a new directory
> > - `mkdir -p [path/directory]`: (make a directory along a path, even when the path doesn't yet exist)
> > - `cd`: change directory
> > - `ls`: list contents of directory
> > - `ls -a`: list all files (including hidden files)
> > - `rmdir [directory_name]`: delete a directory
> > - `pushd [path/directory]`: switch to a new directory, keeping your current directory in a queue for later
> > - `popd`: return to the last directory that you pushed to using `pushd`
> > - `touch [file_name]`: create an empty file
> > - `cp [old_file] [new_file]`: copy a file within a directory
> > - `cp [file] [directory]`: copy a file into a new directory
> > - `mv [old_name] [new_name]`: rename files or directories
> > - `mv [file] [directory]`: move file to a new directory
> > - `cat [file]`: reads a file or files sequentially
> > - `rm [file]`: deletes a file

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

>>`ls`: list contents of a directory...  
`ls -a`: ...including directories beginning with a dot (hidden directories)  
`ls -l`: ...listed in long format  
`ls -lh`: ...listed in long format, using unit suffixes for file sizes  
`ls -lah`: ...including hidden directories, listed in long format, and using unit suffixes for file sizes  
`ls -t`: ...sorted by time modified (most recent first)  
`ls -Glp`: ...listed in long format with colorized output enabled and a slash after each filename if that file is a directory

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

>> `ls -S`: display files sorted by size  
`ls -R`: display all subdirectories  
`ls -m`: display file names as a comma-separated list  
`ls -r`: display files in reverse order  
`ls -x`: display files as rows across the screen  
`ls -1`: display each entry on its own line

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > `xargs` allows you to feed the output of one command as individual inputs for another command. For example, `find . -name "*.txt" | xargs rm` turns the results of the command before the pipe (`find . -name "*.txt"`) into list of arguments to be executed on by the command after `xargs` (`rm`). In this case, we find all the `.txt` files starting from our current directory. Then we delete them. 

 

