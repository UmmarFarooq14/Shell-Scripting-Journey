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

script-2: print a numbers with step-size
---------

	for i in {1..50..2}
	do
	  echo -e "the numbers are:$i"
	done

script-3: Loop over words.
---------

	for fruits in {'banana', 'apple', 'kiwi', 'Orange'}
	do 
	  echo -e "The Fruits are: $fruits"
	done
