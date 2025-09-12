SCRIPT FOR CPU UTILIZATION ALERT:
---------------------------------
 #!/bin/bash
1) Threshold=80;
2) cpu=$(top -bn1 | grep "CPUs" | awk '{ print 100 - $8 }' | cut -d. -f1)
3) if ['$cpu' -gt '$Threshold'];
4) then 
5)    echo "CPU Alert! usage is ${cpu}%."
6) else:
7)    echo "CPU Utilization is Normal: ${cpu}%."
8) fi


SCRIPT FOR DISK UTILIZATION:
----------------------------

#!/bin/bash
1) Thershold=80;
2) disk_usage=$(df/ | awk 'NR==2 { print $5 }' | sed 's/%//')
3) if['$disk_usage' -gt '$Thershold'];
4) then
5)   echo "Disk Alert! Usage is: ${disk_usage}%."
6) else
7)    echo "Disk uage is normal: ${disk_usage}%."
8) fi



