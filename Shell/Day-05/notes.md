1) Nested if:
   ----------
		when one if block placed inside another if then it allows you to check the multiple levels of conditions.

syntax:
-------

	if [condition1]
	then 
	    if [condition2]
	    then 
	        commands
	    else
	        commands
	    fi
	else
	    commands
	fi


script-01: Check if a number is positive and even.
----------

	echo -n "Enter the number:"
	read num
	if [ $num -gt 0 ]
	then
	    if [ $((num % 2)) -eq 0 ]
	    then
	        echo -e " $num is positive & even number."
	    else
	        echo -e "$num is postive $ odd number."
	    fi
	else
	    echo -e "$num is not positive."
	fi


script-02: Check if file exists and is readable.
----------

	echo -n "Enter the name of the file:"
	read filename
	
	if [ -e "$filename" ]
	then
	    if [ -r "$filename" ]
	    then
	        echo -e "$filename file is a exist and has a readable permission."
	    else
	        echo -e "$filename file is a exist and does not a readable permission."
	    fi
	else
	    echo -e "File does not exist!."
	fi

2) Else-if-Ladder:
   ---------------
		when we have multiple conditions, use elif instead of nested if's.

syntax:
-------

	if [condition1]
	then
	    commands
	elif [condition2]
	then
	    commands
	elif [ condition3]
	then
	    commands
	else
	    commands
	fi


script-03: Checking file types.
----------

	filename="sum2.sh"
	if [ -f "$filename" ]
	then 
	    echo -e "$filename  is a file."
	elif [ -d "$filename"]
	then
	    echo -e "$filename is a directory."
	elif [-	L "$filename"]
	then 
	    echo -e "$filename has a symbolic-link."
	else
	   echo -e "File not valid! Check-once name of the file."
	fi
	
