Write a simple shell script (hello.sh) that prints:
---------------------------------------------------
    echo -n "Hello, world!"


Check which shell you are using and list all available shells on your system:
-----------------------------------------------------------------------------

      1) echo $SHELL
      2) echo $0
      3) ps -p $$

      --> cat /etc/shells

Create a directory called practice_day1 and sub-directory is backup & create a three files like file1.txt, file2.txt, file3.log:
-------------------------------------------------------------------------------------------------------------------------------

       mkdir -vp practice-day1/backup
       touch file{1..2}.txt file3.log
       ls -lrth 

 Copy all .txt files to the backup directory:
 --------------------------------------------

      cp  *.txt practice-day1/backup/

 Rename file1.txt → myfile.txt:
 -----------------------------

       mv file1.txt myfile.txt

 Remove file3.log:
 -----------------

      rm file3.log 

Display the absolute path of your current working directory:
-----------------------------------------------------------
      pwd 
      cat /etc/passwd
      less /ect/passwd 
      head -n 5 /etc/passwd
      tail -n 5 /etc/passwd
      touch file3.log

 Write a script that:Defines variables name and age:
 --------------------------------------------------

      name="ummar"
      age=23
      echo -n "My name is $name & I'm $age years old."

 Print the current username and date using command substitution ($())
 --------------------------------------------------------------------
      uname 
      today=$(date)
      echo "Today is :$today"
      echo 'Today is :$(today)'

 Write a script that asks the user for their name (using read) and greets them
 ------------------------------------------------------------------------------

      echo -n "enter the name:"
      read name 
      echo "Hello! $name"

Write a script that asks the user for a number and checks if it is greater than 10 using if
-------------------------------------------------------------------------------------------

      echo -n "enter the number:"
      read num 
      if [ $num -gt 10 ]
      then 
         echo "$num is greather-than 10."
      elif [ $num -ge 10 ]
      then
          echo "$num is equal to 10."
      else
          echo "$num is less-than 10."
      fi

 Run a valid command (like ls) and check its exit status ($?). Then run an invalid command and check again
 ---------------------------------------------------------------------------------------------------------
      command="pwd"
      $command
      status_code=$?
      if [ $status_code -eq 0 ]
      then 
          echo "$command is correct & status_code is: $status_code."
          
      else
          echo "$command is mistake & status_code is: $status_code."
      fi


      command="Ls"
      $command
      status_code=$?
      if [ $status_code -eq 0 ]
      then
          echo "$command is correct & status_code is: $status_code."
      else
         echo "$command is mistake & status_code is: $status_code."
      fi
    
 Use which and type to check the location/type of
 -------------------------------------------------

      type ls 
      location=$(which ls) 
      echo "Location is:$location"
      
      type bash 
      location=$(which bash)
      echo "Location is:$location"
      
      type echo
      location=$(which echo)
      echo "Location is:$location"

 Open the man page of cp and find how to copy a directory recursively
 --------------------------------------------------------------------

      man cp 
      cp -r dir1/ dir2/

 List all files ending with .txt
 -------------------------------

      ls *.txt

 List all files starting with f and ending with any character
 ------------------------------------------------------------

      ls f?.txt

 List only file1.txt, file2.txt, file3.txt using []
 --------------------------------------------------
      ls file[123].txt

 List files that don’t end with .log
 -----------------------------------        

      ls file[!0-9].txt

 Print Hello $USER literally
 ---------------------------

      echo 'Hello! $user'

 Print your username using $USER
 --------------------------------
      name="shaik"
      echo "Hello $name."

Print: It’s 100% done! using escape sequences
----------------------------------------------

      echo  "It\'s 100% done!"

 Print the string *.sh literally without expansion
 -------------------------------------------------

      echo "*.sh"

 Write a script that
 --------------------
      mkdir -v reports
      
      echo -n "enter the name:"
      read name 
      mkdir -vp reports/reports.txt
      ls -lrth reports/ $name date pwd 

Write a script that: Asks the user for two numbers.Prints their sum, difference, and product
--------------------------------------------------------------------------------------------
        echo -n "enter the  two numbers:"
        read a and b
        echo "The sum of $a and &b is: $((a+b))."
        echo "The difference of $a and $b is: $((a-b))."
        echo "The product of $a and $b is: $((a*b))."
        

Ask the user for a filename. If the file exists, print "File exists", otherwise print "File not found"
------------------------------------------------------------------------------------------------------
        echo "Enter the name of the file:"
        read file
        if [ -e "$file" ]
        then 
            echo "File exists."
        else
            echo "File not found."
        fi

Write a script that asks the user for a filename, then:If it exists, display the first 5 lines.If not, print "File does not exist"
----------------------------------------------------------------------------------------------------------------------------------
        echo -n "Enter the filename:"
        read filename
        if [ -f "$filename" ]
        then
            echo "File Exist! Displaying a first 5 lines."
            head -n 5 "$filename"
        else
            echo "File does not exist."
        fi

shell script that asks the user for a filename and then displays the number of lines in that file
--------------------------------------------------------------------------------------------------

        echo -n "Enter the filename:"
        read filename
        if [ -f "$filename" ]
        then
            lines=$(wc -l < filename)
            echo "The file is: $file & has $lines lines."
        else
            echo "File does not Exist."
        fi


script: To check the given number is even or odd.
------

    echo -n "Enter the number:"
    read num
    if [ $((num % 2)) -eq 0 ]
    then 
        echo " $num is a even number."
    else
        echo " $num is a odd  number."
    fi


script: Write a script to check if a number entered by the user is positive, negative, or zero.
------

    echo -n "Enter the number:"
    read num
    
    if [ $num -gt 0 ]
    then
        echo -e "$num is a positive number."
    elif [ $num -eq 0 ]
    then
        echo -e "$num is equal to zero."
    else
        echo -e "$num is a negative number."
    fi


script: Create a script to print all even numbers between 1 and 50.
-------

    echo -n "Displaying Even numbers between 1 to 50."
    
    for (( i=0; i<=50; i++ ))
    do 
      if [ $ ((i % 2)) -eq 0 ]
      then
         echo "The numbers are: $i"
      fi
    done


script: Create a script to calculate the factorial of a given number using a while loop.
------

    echo -n "Factorial of a number is:"
    read num
    factorial=1
    for (( i=1 ; i<=num; i++ ))
    do
       factorial= $((factorial*i))
       echo "The factorial of a number is: $factorial"
       
    done

script: Create a script to calculate the factorial of a given number using a while loop.
-------

    echo -n "Enter the number:"
    read num
    
    factorial=1
    i=$num
    
    while [ $i -gt 0 ]
    do 
      factorial=$((factorial*i))
      i=$((i-1))
    done
    
    echo -e "The Factorial of $num is:$factorial."

script: Create a nested loop to display a multiplication table for numbers 1 to 5.
-------

    for (( i=1; i<=10; i++ ))
    do
      for(( j=1; j<=5; j++))
      do 
        echo "$i*$j=$((i*j))"
      done
     echo "Exit!"
    done

script: Write a script to sum all numbers from 1 to 100.
-------

    sum=0
    for (( i=1; i<=100; i++ ))
    do
      sum= $((sum+i))
    done
    echo "The sum of numbers is: $sum"



      
