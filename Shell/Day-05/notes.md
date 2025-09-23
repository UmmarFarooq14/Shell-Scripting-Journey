Nested if:
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
