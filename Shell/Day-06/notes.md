what are loops:
---------------
	  A loop is a control structure that repeadtly executes a block of code until condition gets true.

In Shell Scripting, common loops are:
-------------------------------------
	1) For loop
	2) while loop
	3) until loop


1) For loop:
   ---------
syntax:
-------
	for variables in list
	do
	  commands
	done

script-1: print a numbers with step-size
---------

	for i in {1..50..2}
	do
	  echo -e "the numbers are:$i"
	done

script-2: Loop over words.
---------

	for fruits in 'banana', 'apple', 'kiwi', 'Orange'
	do 
	  echo -e "The Fruits are: $fruits"
	done

script-3: Loop through files.
---------

	for files in *.sh
	do
	  echo -e "script files: $files"
	done

script-4: loop over logged-in users.
--------

	for users in $(who | awk '{ print $1 }')
	do
	  echo -e "Logged-in users are: $users"
	done

script-5: Monitoring cpu usage
---------

	while true
	do
	  cpu=$(top -bn1 | grep -i"CPU(s)" | awk '{print 100-$8}')
	  echo -e "CPU usage is: ${cpu}%"
	  sleep 2
	done
	
script-6: disk uage of a file system.
---------

while true
do 
  disk_usage=$(df -h . | awk 'NR==2 {Print $3, $4, $5}')
  echo "disk_usage is: $disk_usage"
  sleep 2
done
