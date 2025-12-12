SCP- Secure Copy Protocol:
--------------------------
    . The secure copy protocol (or) "scp" helps to transfer computer files securely from a local to a remote host. It is somewhat similar to the file transfer pratical "FTP", but it adds security and authentication.

     . protocol = set of rules used by computers to communicate.
     . Default scp port = 22
     . For this we need 2 linux machines
           . client = MyfirstlinuxVM
           . server = Linuxcentos7

rsync- Remote Synchtanization:
------------------------------
    . rysnc is a utility for efficiently transferring & synchronzing files within the same computer (or) to a remote computer by comparing the modification times and sizess of files.
    
          . rysnc is a lot faster than ftp (or) scp.
          . This utility is mostly used to backup the files and directories from one server to another .
          . Default rysnc port = 22
          
        Syntax:
        ------
            rsync -avz filename username@Ipaddress: location 

DNS:-Domain Name System
-----------------------
    Hostname
      . PTR Record     (IP  to  Hostname)
      . A Record       (Hostname to IP)
      . CNAME          (Hostname to Hostname)

     Files:
     ------
       . /etc/named.conf
       . /var/named

    service:
    --------
       . systemctl restart named

    Hostname / IP Lookup:
    ---------------------

        . commands use dfor DNS lookup
             . nslookup(Name Server lookup) for a domain IP
             . dig (domain Interface groper)

       
NTP:- Network Time Protocol (or) chronyd:
----------------------------------------
      . Purpose:
           Time Synchronization.
       
      . File:
          /etc/ntp.conf

      . service:
           systemctl restart ntpd.

      . port:- 123

      . command:
            ntpd

Central Logger:
---------------
    Purpose:
       . Generate logs (or) collect logs from other server.

    Service (or) Package name:
        . rsyslog
        
    Configuration File:
        . /etc/rsyslog.conf

    Service:
    
        

