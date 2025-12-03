Client & Server Relationship:-
-----------------------------
Client:
------
    A clinet is a computer (or) a program that, as part of its operation, relis on sending a request to another program (or) a computer hardware (or) software that access a service made availability by a server.

Server:
-------
    Server is a piece of computer hardware (or) software that provides functionality for other programs (or) devices, called clients.

Network Components:
-------------------
     * IP                        * Gateway                             * Interface
     * Subnet Mask               * Static vs .DHCP                     * Inteface MAC

Network Files & COmmands:
-------------------------
    * Inteface Detection.
    * Assigning an IP address.
    * Interface Configurstion files.
         . /etc/nsswitch.conf
         . /etc/hosts
         . /etc/sysconfig/network
         . /etc/sysconfig/network-scripts/ifcfg-nic
         . /etc/resolv.conf
         
NIC-Network Interface card:
---------------------------
    lo = The loopback dwvice is a special interface that your computer uses to communicate with itself. It is used mainly for diagnostics and troubleshooting and to connect to servers running on the local  machine.

    vibro = The vibro, (or) "virtual bridge o" interface is ud=sed for NAT(Network Address Translation). virtual environments sometimes uses it to connect to the outside network.

Configure & Secure SSH:
-----------------------

    SSH Stands for Secure shell.
    
    * Provides you with an interface to the linux system. It takes in your commands and translate them to kernel to manage hardware.

    * SSH iteself is secure, meaning communication through SSH is always encrypted, but there should be same additional configuration can be done to make it more secure.

    * Following are the most common configuration an administrator should take to secure SSH.

    => Configure Idle Timeout Interal.
    
     AVoid having an unattended SSH Session, you can sat an Idle timeout interval.

         => Become root.
         => Edit your /etc/ssh/sshd_config file and add the following line:
         => ClientAlive Interval 600.
         => ClientAlive count 0.
         => # Systemctl restart sshd.
    * The Idle timeout interval you are setting in seconds (600sces  =10 minutes). once the interval has passed, the idle user will be automatically logged out.

    
Disable root login:
-------------------
    * Disable root login should be one of the measures you should take when setting up the system for the first time. It disable any user to login to the system with the root account.
       => Become root.
       => Edit you /etc/ssh/sshd_config file & replace permit root login  yes to no.
       => permit root login no.
       => # Systemctl restart sshd.

Disable Empty Passwords:
------------------------
    * You need to prevent remote logins from accounts with empty passwords fro added security.
        => Become root.
        => Edit your /etc/ssh/sshd_config file & remove  # from the following line.
        => permit empty passwords no.
        => # Systemctl restart sshd.

Limit User's SSh access:
------------------------
* To prevent another layer of security, you should limit your sshd logins to only certain users who need remote access.
       
  


  
    
