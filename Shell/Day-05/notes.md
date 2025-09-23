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

3) Case Statement:
   ---------------
		The case statement is used when we need to match a value against multiple patterns. It’s more readable than long elif ladders.

syntax:
------
	case Variable in
	      pattern1)
	          commands  ;;
	      pattern2)
	          commands  ;;
	      pattern3)
	          commands  ;;
	      pattern4)
	          commands  ;;
	      *)
	          commands  ;;
	easc


script-04: Day of the week.
----------
	day=$(date +%a)
	
	case $day in
	       Mon) 
		      echo -e "Starting of the week." ;;
		   Tue)
		      echo -e "Second day of the week!"
	       Fri) 
		      echo -e "Weekend is next day!."  ;;
		Sat|Sun)
		     echo -e "Weekend!." ;;
		    *)
			  echo  -e "Mid of the week!." ;;
	esac
	   

script-05: Menu-driven program.
----------

	echo -n """ ***Menu*** """
	echo -e "1.Show current date."
	echo -e "2.show current working directory."
	echo -e "3.show logged-in user."
	echo -e "4.Operating system-version."
	echo -e "Select the choice:"
	read choice
	
	case $choice in
	        1) date ;;
	        2) pwd  ;;
	        3) who  ;;
	        4) cat /etc/os-release ;;
	        5) echo "Existing!...." ;;
	        *) echo "-----Invalid Choice----" ;;
	esac


script-06: Calculator using case statement.
---------

	echo -e """**** CALCULATOR ****"""
	echo -e "1.Addition of numbers."
	echo -e "2.Subtraction of numbers."
	echo -e "3.Multiplication of numbers."
	echo -e "4.Division of numbers."
	echo -e "Select the choice:"
	read choice
	echo -e "Enter the numbers:"
	read a b
	
	case $choice in
	           1)
	            echo -e "The Sum of numbers is: $((a+b))" ;;
	           2)
	            echo -e "The Diff of number is: $((a-b))" ;;
	           3)
	            echo -e "The Mul of number is: $((a*b))" ;;
	           4)
	            echo -e "The Division of number si: $((a/b))" ;;
	           5)
	            echo -e "Invalid choice!." ;;
	esac

	
