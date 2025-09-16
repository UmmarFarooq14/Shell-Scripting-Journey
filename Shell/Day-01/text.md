What is Shell:
--------------
	A Shell is a program that acts as a interface between user and operating system and it allows user to interact with OS using commands like ls, pwd, touch, cd.

What is Bash:
------------
	Bash is default shell present in the Linux/Centos/Ubuntu to execute the commands and scripts in OS & Bash(Bourne Again Shell) is the updated version sh(Bourne Shell).

Types of Shells:
---------------
1) SH  (Bourne Shell)--> Stephen Bourne in 1977 at Bell Labs.
2) BASH(Bourne Again Shell)
3) KSH (Korn Shell)
4) CSH ()
5) ZSH ()
6) FISH (Friendly Interactive Shell)

To display the shells installed in OS:
------------------------------------
command:
--------

	cat /etc/shells


To display the current shell:
----------------------------
command:
-------

	echo $SHELL


Shell Scripts:
--------------

	Shell Script is a text file contains the group of Linux commands in order to perform the task.


Extension of Shell Script:
-------------------------
	.sh


There are 4 ways to executable a Shell Script:
---------------------------------------------
1) sh file-name.sh
2) ./file-name.sh
3) . file-name.sh
4) bash file-name.sh


Steps to run the shell script:
------------------------------
Step-1: Create a file/directory and add extension as .sh.


To create a file:
----------------
command:
--------
	touch file-name.
	cat > file-name.
	vi/vim file-name. 

To create a directory:
----------------------
command:
-------
	mkdir -pv directory-name.

1) -p ---> to create as a parent directory.
2) -v ---> to display the message of directory is created.


Step-2: Insert Linux commands/ text inside the file.

Ex:-
----
	vi file-name
--> It will open the file in vi editor--> Press i (To change into insert mode) --> then add the text --> press :wq!(w-->save, q--> quit).


Step-3: Check the file permission before execution.

command:
--------
	ls -l 

Explanation:
------------

	It will display the all files and permissions of files including date, time of creation.



Scenario:
---------
	 If file doesn't contain the execute permission. Then add the execute permission using chmod command.


command:
-------
	chmod u+x file-name.


Explanation:
------------
	This command adds the  execute permission to user.(u-->user , x--->execute-code(1)).
