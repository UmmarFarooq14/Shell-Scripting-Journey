
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

	echo -s "enter the password:"
	read passwd
	echo -n "The password is: $passwd"


script-4: with prompts without read
-------- 
	read -p "Enter the city:" $city
	echo "My city is: $city."


script-5: set time-out for Input.
--------
	echo -t 5 "Enter the software you are learning:"
	read "software-name"
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

--> press space to scroll down.
--> press b to scroll up.
--> press q to quit.


 
