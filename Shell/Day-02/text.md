Basic Linux Commands:
---------------------

ls:
---
	It will display the files & directories in current path.

Features of ls:
---------------

	ls -l   # It will display the files & directories along with Premissions and time, date of creation.
	ls -la  # It will display all the files including all the hidden files.
	ls -li  # It will display the inode numbers of each file.
	ls -lh  # It will display all the files/directories in human-readable size (kb, mb, gb)
	ls -lr  # It will display all the files/directories in reverse order.
	ls -lt  # It will display the files/directories in table format.

cd:
---
	Change the directory.

Features of cd:
---------------
	cd ~      # It will go to home directories.
	cd        # It will go to home directories.
	cd -      # It will get back to previous file/directories.
	cd ../    # It will get back one step to previous stage.
	cd ../../ # It will get back two steps to previous stage.

pwd:
----
	Shows the current working directory path.




mkdir:
-----
	used to create a directory.


Features of mkdir:
-----------------
	mkdir -v directory-name      # It will create a directory and display the directory is created.
	mkdir -p dir1/dir1/dir1      # It will create a multiple directories at a time inside the dir1.



rmdir:
------
	To remove empty directories.

Features of rmdir:
------------------
	rmdir             # removes empty directory.
	rmdir -rf         # to remove non-empty directory.
	rmdir dir1/dir2   # removes only empty directory.


touch:
------
	It is Used to create a empty file.
	
Features of touch:
------------------	

	touch file-name                # It will create a empty file
	touch file-name1 file-name2    # It will create a two empty files.


cp:
---
	copying a files from one location to another & also copying from files to directories.

Features of cp:
---------------

	cp file1 file2          # copying a data from file1 to file2.
	cp file1 dir1/          # copying a data from file1 to inside the dir1.
	cp -r dir1/ dir2/       # copying a data from dir1 to dir2.


mv:
---
	move (or) rename a file/dir.

Features of mv:
---------------

	mv file1 dir1/       # moving a file1 to inside the dir1.
	mv file1 file1.txt   # renaming a file.

rm:
---
	removing a file/dir.

Features of rm:
--------------
	
	rm file1      # deleting a file1.
	rm -r file1   # deleting a file1 recursevily.
	rm -i file1   # before it ask to user that I'm deleting a file1.
	rm -rf file1  # removing a file recursevily & forcefully.



File & Directory Permission:
---------------------------

	Every file/directory  has a it's own permission.

Permissions:
------------

	Every file/dir in linux has three set of  permissions. 

1) User(owner) -- rwx -7
2) group --rwx -7
3) Others --rwx -7

	1) R-->Read     -->4
	2) W-->Write    -->2
	3) X-->execute  -->1

	File Permission will be depend on the Umask number by default umask number is 0022 and default umask number for file is 0666 & Default umask number for directory is 0777.

For Directories:
---------------

                                   0777
	                               0022
                                  ------
	Default dir permission:	       0755
                                  ------

For File:
---------


                                 0666
                                 0022
                                -------
	Default file permission:     0644 
                                -------

--> We can change the file permission using a chmod command.

command:
--------

	chmod g+r filename.        # This command will add a read permission to group.
	chmod g-x filename.        # This command wiil remove a execute permission for group.



chown:
-----
	To change the ownership of the file/dir.


command:
--------
	sudo chown newuser file.txt        # change owner
	sudo chown newuser:newgroup file.txt



chgrp:
-----
	To change the ownership of group.

command:
--------
	chgrp group_name file_name.


cat:
----
	Is used to display the content inside the file and creation of file and also concatenate.

Fetures of cat:
---------------

	cat file-name                                  # It will display the data inside the file.
	cat > file-name                                # It will create and adds the data inside the file. (ctr+d)
	cat file-name1 > file-name2                    # It will over-write the data in file-name2 with data in file-name1.
	cat file-name1 >> file-name2                   # It will append the data of file-name2 with data file-name1.
	cat file-name1 file-name2 > file-name3         # It will add the data of file-name1 & file-name2 into file-name3.

less:
-----
	view file (Scorable) 

command:
--------
	less file-name



more:
-----
	view file (like less, but it is older)

command:
--------
	more file-name



head:
-----
	It will diaplay the first few lines.


Feature of head:
----------------
	head file-name               # It will display the first 10 lines of a file.
	head -n 5 file-name          # It will display the first 5 lines of a file.



tail:
-----
	It will display the bottom 10 lines.


Fetaures of tail:
-----------------

	tail file-name              # It will display the bottom 10 lines.
	tail -n 6 file-name         # It will display the bottom 6 lines.



echo:
-----
	print text to a terminal.

Features of echo:
-----------------
	echo -n      # Don't add a new line at the end.
	echo -e      # Allow special characters like '/n' for a new line.
	echo -E      # Don't allow special characters/disables the use of backslash escapes.
