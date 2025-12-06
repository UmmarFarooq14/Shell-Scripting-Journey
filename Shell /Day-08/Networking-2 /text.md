FTP: File Transfer Protocol:
----------------------------
     * The FTP is a standard network protocol used for the transfer of computer files b/w a client & server on a computer network. FTP is built on a client-server on a computer network. FTP is built on a client-server model architecture using seperate control and data connctions b/w the client & server.
     
         => protocol = set of rules used by computers to commmunicate.
         => Default FTP port = 21
         => For this we need 2 Linux Machines.
             . Client = MyFirstLinuxVM
             . Server = LinuxCentos7
        => Install and configure FTP on the remote server.
             . # Become root.
             . # rpm -ga | grep ftp
             . # yum install vsftpd
             . # vi /etc/vsftpd/vsftpd.conf

        => Install ftp client on the client server.
           . # Become root.
           . # yum install ftp.
           . # su - username.
           . # $ touch kruger
    
        
