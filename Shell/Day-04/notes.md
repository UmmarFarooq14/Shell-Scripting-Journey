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






