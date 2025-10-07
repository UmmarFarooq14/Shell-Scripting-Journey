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
           Thershold=80
           cnt=1
           while read -r filesystem size use avail usep mountpoint
           do 
             usage_percent=$(echo "$usep" | tr -d '%')
             if [ "$usage_percent" -gt "$Thershold" ]
             then
                 echo "Disk_Usage Alert! & Usage is: $filesystem  $usep  $mountpoint"
                 cnt=1
            fi
          done < <(df -h --output=source,sixe,use,avail,pcent,target | awk 'NR>1')
          if [ "$cnt" -eq 0 ] 
          then
              echo -e "Disk_usage is normal :(<= {Thershold}%)"
          fi


Log-Monitoring Script:
----------------------


      # !/bin/bash
      log_file="/var/log/syslog"
      if [ ! -f "$log_file" ]
      then
          echo "Error! $log_file doesn't exist and cannot be accessed."
          exit 1
      fi
      error_count=$( grep -i "error" "$log_file" | wc -l )
      echo -e "Warning! $error_count found in $log_file."

Cleaning the all the files older than 7 days:
---------------------------------------------

      # !/bin/bash
      log_dir=""
      find "$log_dir" -type f -name "*.sh" -mtime +7 -exec rm -f {} \;
      echo -e "files are cleaned older than the 7 days from $log_dir."
      # find "$log_dir" -type f -name "*.sh" -mtime +7   #  used to display the files older than days.

To Display the list of users in server:
---------------------------------------
      # !/bin/bash
      for users in $(w | awk '{ print $1 }') 
      do
        echo "The list of users are:$users"
      done
          echo "Exit!"
