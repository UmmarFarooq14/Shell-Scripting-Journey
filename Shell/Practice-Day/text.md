Write a simple shell script (hello.sh) that prints:
---------------------------------------------------
    echo -n "Hello, world!"


Check which shell you are using and list all available shells on your system:
-----------------------------------------------------------------------------

      1) echo $SHELL
      2) echo $0
      3) ps -p $$

      --> cat /etc/shells

Create a directory called practice_day1 and sub-directory is backup & create a three files like file1.txt, file2.txt, file3.log
-------------------------------------------------------------------------------------------------------------------------------

    mkdir -vp practice-day1/backup
    touch file{1..2}.txt file3.log
    ls -lrth 

# Copy all .txt files to the backup directory.

  cp  *.txt practice-day1/backup/

# Rename file1.txt → myfile.txt.

   mv file1.txt myfile.txt

# Remove file3.log.

  rm file3.log 

# Display the absolute path of your current working directory.
  pwd 

  #cat /etc/passwd
  #less /ect/passwd 
  #head -n 5 | cat /etc/passwd
  #tail -n 5 | /etc/passwd


  touch file3.log

# Write a script that:Defines variables name and age.

  name="ummar"
  age=23
  echo -n "My name is $name & I'm $age years old."

# Print the current username and date using command substitution ($()).
  uname 
  
  today=$(date)
  echo "Today is :$today"
  
  echo 'Today is :$(today)'

# Write a script that asks the user for their name (using read) and greets them.

  echo -n "enter the name:"
  read name 
  echo "Hello! $name"

# Write a script that asks the user for a number and checks if it is greater than 10 using if.

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

# Run a valid command (like ls) and check its exit status ($?). Then run an invalid command and check again.
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
    
# Use which and type to check the location/type of:

  type ls 
  location=$(which ls) 
  echo "Location is:$location"
  
  type bash 
  location=$(which bash)
  echo "Location is:$location"
  
  type echo
  location=$(which echo)
  echo "Location is:$location"

# Open the man page of cp and find how to copy a directory recursively.

  man cp 
  
  cp -r dir1/ dir2/

# List all files ending with .txt.

  ls *.txt

# List all files starting with f and ending with any character.

  ls f?.txt

# List only file1.txt, file2.txt, file3.txt using [].
  ls file[123].txt

# List files that don’t end with .log.

  ls file[!0-9].txt

# Print Hello $USER literally.

  echo 'Hello! $user'

# Print your username using $USER.
  name="shaik"
  echo "Hello $name."

# Print: It’s 100% done! using escape sequences.

  echo  "It\'s 100% done!"

# Print the string *.sh literally without expansion.

  echo "*.sh"

# Write a script that:
  mkdir -v reports
  
  echo -n "enter the name:"
  read name 
  mkdir -vp reports/reports.txt
  ls -lrth reports/ $name date pwd 
