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



