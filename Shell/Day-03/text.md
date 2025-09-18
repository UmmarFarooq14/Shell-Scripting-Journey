
Variables in Shell:
-------------------

Defining & Using variables:
---------------------------
	A variable is used to store the data in memory for reusing the sama data  inside the scripts. 
--> While assigning the value to a variable no spaces allowed around it.


script-1:
---------
	echo -e "Hi \n Hello"

script-2:
---------
	greeting="Hi Welcome to Shell World."
	echo "$greeting"


script-3:
--------
	name='Ummar'
	age=23
	echo -n "My name is: $name and age is: $age "


Environment Variables:
----------------------
	Environment variables are system-wide variables available for all processess and shells.


To View the all Environment Variables:
--------------------------------------
command:
--------
	env


Some Common Environment variables:
----------------------------------
	echo $Home                # home directory.
	echo $USER                # To list the user-loging.
	echo $SHELL               # To display current shell.
	echo $path                # search for the current path.



script: set an environment variable.
------
	export course ="Shell Scripting."
	echo -n "$course"  



Command Substitution:
--------------------

	command substitution let you store the output of a command into a variable.     

Method-1: 
--------
	today=$(date)
	echo -n "The date is :$today" 

Method-2:
--------
	today=`date`
	echo -n "The date is :$today"  



USer Input & Exit Status:
------------------------
read command:
------------
	It will read the input from user and store in a variable.

script-1: reading a name 
---------
	echo -n "Enter the name:"
	read name
	echo "Hello! My name is:$name." 


script-2: reading the two numbers
--------
 	echo -n "Enter the two numbers:"
	read a b
	echo -e "The value of a is:$a \n The value of b is: $b."


script-3: silent Input (It won't display the password on terminal)
-------- 

	read -s -p"enter the password:" passwd
	echo -n "The password is: $passwd"


script-4: with prompts without read
-------- 
	read -p "Enter the city:" city
	echo "My city is: $city."


script-5: set time-out for Input.
--------
	read -t 5 -p "Enter the software you are learning:" software-name
	echo "I'm learning a:$software-name."

script-6: Limit Input upto N-character.
--------
	read -n 3 -p "enter the 3-letter text:" $text
	echo "you entered is: $ text"

script-7: reading from a file.
--------
	while read line;
	do:
	   echo "Line: $line"
	done < /etc/passwd
	



Exit Status:
------------
	Every command in linux returns an exit status code.
 

--> If status code is 0       --- Success 
--> If status code is (1-225) --- Failure.

script-1: For success
-------
	pwd 
	echo $?


script-2: For Failure
--------
	Ls -la
	echo $?

script-3: To check the file is exit or not exist in server.
---------

	ls /etc/passwd

	if [ $?  -eq 0]
	then
   	 	echo "File is exist!."
	else
    	echo "File is not exist!."
	fi 


which command:
--------------
	shows the full path of an executable command and helpful to check the whether command/program is located.

command:
--------
	which bash
output:
-------
	/bin/bash

command:
--------
	which python3

output:
-------
	/usr/bin/python3




type command:
-------------
	Display a command how it is interpreted by a shell & expalins about the if a command is built-in, an alias or a external program.

command:
--------
	type ls           # ls is aliased to 'ls --color=auto'
	type bash         # bash is /bin/bash.

man command: (Manual Pages)
----------- 
	man command is used helpful for the more abouth the linux command.

command:
--------
	man ls

1) press space to scroll down.
2) press b to scroll up.
3) press q to quit.



wildcard (Globbing):
-------------------
	wildcards are the special characters in linux/unix shell that used to match the patterns when working with files/directories is called Globbing.


1) * --> Matches zeros or more characters:
     --------------------------------------

--> Match including everything including a empty string.

	ls *.txt     # It will display all files end with .txt 
	ls file*     # It will display all the files like file1, file2, file3 ..
	ls *         # It will display all the files/dir in current directory.


2) ? --> Matches exactly one character:
   ------------------------------------

--> Matches any single character (except hidden files starting with . unless explicity specified)

	ls ?.txt             # matches a.txt, b.txt but not abc.txt.
	ls file?             # matches the file1, file2 but not file10.


3) [] --> Matches a one character from set/range:
   -------------------------------------------------

--> Use [] for set or range.

	ls file[123].txt     # matches file1.txt, file2.txt, file3.txt.
	ls file[a-c].txt     # matches filea.txt, fileb.txt, filec.txt.
	ls file[!0-9].txt    # macthes all the files except from file0,...file9.


Note:
-----
	Globbing is handled by the shell before executing the command.
	If no files match the pattern some shells return the literal string (ls *.xyz)other may return an error.


Quoting in Shell:
-----------------
	It is used to controlling how the shell interprets special characters (*, ?, $, !, /, etc).

1) Single Quote.
2) Double Quote.
3) Backslash.


1) Single Quotes :
   ---------------
	Everything inside the single quote is literally and No variable expansion and no command substitution.

script:
-------
	echo -n 'Enter the name'

2) Double Quotes :
   ---------------
	preserves most character literally but allows variable expansion and command substitution.

script:
-------
	echo -e "The value of a is: $a \n The value of b is: $b"
	echo -n "Today date is:$(date)"


3) Backslash:
   ----------

	Escapes the special meaning of the next character only.

script:
-------
	echo "My name is \$name."
	echo "It\'s very nice."

Note:
-----
	If we want to combine both literal text & Variable expansion in a singlke command.

script:
-------
	echo 'My name is:' "$name"


 
