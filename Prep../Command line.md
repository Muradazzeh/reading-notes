# The command line 
first we have two type of user interface 
* GUI : graghical user inter face 
* CLI : command line interface .

> so the command line interface is text base interface between the user and the system and the feed back will be text too.

 we can start with command echo $shell so we now display a system variable stating your current shell  
 ![link](./commndline%20image/Screenshot%20(55).png)

 > note : when we entered command it will be saved in the history we can checke them by us ing up and down arrow on the keyboard.

  ## Navigation 
  we will start learning command line 
  * pwd : print work directory : this command will tell you your present directory.
  * ls : shortcut for listing : it will list all file and folder in your location 
  - ls -l : this command will do long listing.
  - ls /etc : it will list directory content not our directory .

  ### Path
   we have two type of path :
   * Absolute path : a file or directory location in relation to the root of the file system .
   * Relative path : a file or directory location relatice to  where we currently are in the file system .

   **About path** 
   * ~ (tilde) - This is a shortcut for your home directory.
   * . (dot) - This is a reference to your current directory
   * .. (dotdot)- This is a reference to the parent directory

   **path command**

   cd [location] : stand for change directory :move to another directory.

   > note :Tab Completion we use tab to completed the requierd word in the command line.

   ##  More about File 
   everything  in the linux is actually a file.
   and we have some type of files 
   * file.exe : excutable file 
   * file.txt : text file type 
   * file.png , file.jpg , file.gif : image type 

   **file command**

   file [path]: obtain information about what type of file a file or directory is.
   ![link](./commndline%20image/Screenshot%20(56).png)

   ### Hidden file and directory .
   we can use this command to check it 
   * ls -a List the contents of a directory, including hidden files. 

   ## manual pages
   are set of page that explaine every command available on the system . 
   * man <'command to look up'>: it will show details for the command
   * man -k <'search'>: if we want to search withen the manulas
   * /<'term'> : withen manual page perform a search for term 
   * n : after search select next found item .
![link](./commndline%20image/Screenshot%20(58).png)


## File Manipulation
we will start with the command.

1 -  mkdir [options] <'Directory'> : make directory : it will make new directory in your current location 
* mkdir -p : it will make pairent directory as needed .
* mkdir -v : it will show us what mkdir command doing .

2- rmdir [options] <'Directory'> : remove directory : it will remove the current directory .
* rmdir -p : it will remove pairent directory as needed
* mkdir -v : it will show us what rmdir command doing .

3- also we can creat file using command 
* touch <'file name'>

4- we can copy file or directory  
* cp [options] <'source'> <'destination'>

5- we can move file or directory 
* mv [options] <'source'> <'destination'>
* also we can use mv  to rename file or directory 

6- we can remove files by using :
* rm [options] <'file'>: this is for empty file 
* rm -r : r stand for recursive : we can remove non empty file .
![link](./commndline%20image/Screenshot%20(60).png)
 > note : No undo
The Linux command line does not have an undo feature. Perform destructive actions carefully.










