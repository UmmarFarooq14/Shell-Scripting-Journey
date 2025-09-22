Control Structures & Loops in Shell Scripting:
----------------------------------------------
Introduction:
------------
	  In Programming, control structures allows us make to take decisions and perform loops.

  1) if, else, elif
  2) for loops

syntax  for if -ellse:
----------------------

	if [           ]
	then 
	    echo "       "
	else
	    echo "       "
	fi
 

syntax for elif:
----------------

	if [              ]
	then 
	    echo "        "
	elif [            ]
	then 
	    echo "        "
	else
	    echo "        " 
	fi 

script-1: Check the number is +ve or -ve.
---------

	echo -n "Enter the number:"
	read num
	
	if [ $num -gt 0 ]
	then
	    echo " $num is +ve."
	else
	    echo " $num is -ve."
	fi

script-2: Grading System.
---------

	echo -n "Enter the marks:"
	read marks
	
	if [ $marks -gt 90 ]
	then
	    echo "For $marks marks Grade is: A."
	elif [[ $marks -gt 75 && $marks -lt 90 ]]
	then
	    echo "For $marks marks Grade is: B."
	else
	    echo "For $marks marks Grade is: C."
	fi


Operators in Shell:
-------------------
Integers comparison operator:
-----------------------------

	-eq                        # Equal to operator.
	-ne                        # Not-equal to operator.
	-lt                        # Less-than operator.
	-gt                        # Greater-than operator.
	-le                        # Less-than or equal to operator.
	-ge                        # Greater-than or equal to operator.


script-3: comparison of two numbers.
---------

	a=10
	b=20
	if [ $a -gt $b ]
	then
	    echo "$a is greater than $b."
	else
	    echo "$b is greater then $a."
	fi

 String comparison operator:
--------------------------

	 =                          # Equal.
	!=                          # Not-equal.
	-z                          # String is empty.
	-n                          # string is not empty.


script-4: To check whether the string is empty or not.
---------

	string="Hello"
	if [ -n "$string" ]
	then 
	    echo "$String is not empty."
	else
	    echo "$String is empty."
	fi

Files Test Operators:
--------------------

	-f                       # To check the file.
	-d                       # To check the directory.
	-e                       # To check the file if truly exists.
	-r                       # To chelc the file has readable permission or not.
	-x                       # To check the file has executable permission or not.
	-w                       # To check the file has write permission or not.
 

script-5: To check whether it is a file or not.
--------

	file="sum.sh"
	if [ -f "$file" ]
	then
	    echo "$file is a file."
	else
	    echo "$file is not a file."
	fi


script-6:  To check whether it is a directory or not.
---------

	file="data"
	if [ -d "$file" ]
	then
	    echo "It is a directory."
	else:
	    echo "It is not a directory."
	fi


script-7: To check whether the file has a read permission or not.
---------

	file="sum.sh"
	if [ -r "$file" ]
	then 
	    echo "The $file file has a read permission."
	else
	    echo "The $ file doesn't have a read permission."
	fi


script -8: To check whether the file has a execute permission or  not.
----------

	file="sum.sh"
	if [ -x "$file" ]
	then
	    echo "The $file file has a executable permission."
	else
	    echo "The $file file doesn't have a executable permission."
	fi


script-9: To chekc whether the file has a write permission or not.
---------

	file="sum.sh"
	if [ -w "$file" ]
	then
	    echo "The $file file has a write permission."
	else
	    echo "The $file file doesn't have a write permission."
	fi

Loops in Shell:
--------------
	1) For Loop.
	2) While Loop.


 1) For Loop:
    ---------
	Used to iterate over list of items until the condition gets false.


syntax for for loop:
--------------------

	for var in lists
	do 
	  echo "     "
	done

script-10: To display the numbers from 1-10.
----------
	for i in {1..10}
	do 
	  echo -e "The number are: $i."
	done

script-11: Loop over files.
----------

	for files in "*.sh"
	do 
	  echo -e "The files are: $files.
	done

2) While Loop:
--------------

	Executes commands until unless condition gets true.

syntax for While:
-----------------

	while [  ] 
	do
	  echo "   "
	  condition;
	done

script-12: To print numbers from 1-5.
----------

	i=5
	while [ $i -le 5 ]
	do 
	  echo -e "The number is: $i."
	  i=$((i+1))
	done

script-13: While Loopusing a break statement.
----------

	i=0
	while [ $i -le 5 ]
	do
	    echo "The number is: $i."
	    if [ "$i" -eq 3 ]
	    then 
	        echo "Breaking the loop."
	        break
	    fi
	    i=$((i+1))
	done

