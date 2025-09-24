SCRIPT FOR CPU UTILIZATION ALERT:
---------------------------------
      #!/bin/bash
     Threshold=80;
     cpu=$(top -bn1 | grep "CPU(s)" | awk '{ print 100 - $8 }' | cut -d. -f1)
     if ["$cpu" -gt "$Threshold"]
     then 
         echo "CPU Alert! usage is: ${cpu}%." | mail -s "High alert!" shaikummarfarooq138@gmail.com
     else
         echo "CPU Utilization is Normal: ${cpu}%."
     fi


SCRIPT FOR DISK UTILIZATION:
----------------------------

     #!/bin/bash
     Thershold=80;
     disk_usage=$(df/ | awk 'NR==2 { print $5 }' | sed 's/%//')
     if["$disk_usage" -gt "$Thershold"];
     then
       echo "Disk Alert! Usage is: ${disk_usage}%."
     else
       echo "Disk uage is normal: ${disk_usage}%."
     fi



