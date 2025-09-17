
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
