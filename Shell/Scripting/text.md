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

