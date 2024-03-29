# LINUX-ADMIN
                                                        NEW TOPIC FTP

#FILE TRANSFER PROTOCOL  
#The File Transfer Protocol is a communication protocol used for the transfer of computer files between a client and server on a computer network.

#Uses  TCP/IP
#Port 20/21
#FTP also used to upload/download files from websites and servers.

=========================================================================================================================================
REMOTE SERVER FTO SETUP:
1. go to check your system vsftpd install check.

    Rpm -qa | grep -i vsftpd

2. go to install vsftpd,

     yum install vsftpd


->> PERMISSON

Note: You have to any change in first backup your file /etc/vsftpd/vsftpd.conf.
 
             cp  vsftpd.conf      vsftpd.conf.org     


3. go to changes /etc/vsftpd/vsftpd.conf  and give the permissions.

    Anonymouns_enable=No                         --- LOGIN OR NOT
             
    ascii_upload_enable=YES                       --- ANY PERSION NOT UPLOAD
    ascii_download_enable=YES                   ---ANY PERSION NOT DOWNLOAD
    
    chroot_local_user=yes


-->>    HOW TO BLOCK FTP USERS
  
        vi  /etc/vsftpd/ftpusers  Type user name
        ramu
        jais



========================================================================================================================================
-->> Note:   YOUR COMPANY REQUARMENT ANY CUSTOMER GIVE THE FTP     
 PERMISSON.
 
1. go to create partition  fdisk  /data       5GB
2. useradd      -d    /data/folder      username
3. data copy  dump   /data/folder
4.  go to vsftpd.conf       change   chroot
5.  go to   ftp create user and set password  AND Public IP Send customer.



4. go to start and enable vsftpd service.
    
    systemctl start vsftpd
    systemctl enable vsftpd

5. Go to check vsftpd status.

   systemctl  status vsftpd

6. go to stop or allow FTP to Firewall
We will temorarily stop firewall

   systemctl  stop firewall


--->>> ACTIVE FTP AND PASSIVE FTP
  ACTIVE 
1. Connection  21 port
2. data transfer  20 port      

PASSIVE
1. Connection  21 port
2. data transfer   HIGHER PORT   1024   to  65535
   
--->>> HOW TO CHANGE ACTIVE FTP TO PASSIVE FTP

go to vi   /etc/vsftpd/vsftpd.conf

=========================================================================================================================================
-->> CLIENT SERVER FTP SETUP:
1. go to check your system ftp install check.

    rpm -qa | grep -i ftp


 2. go to install ftp,

     yum install ftp

3. go to open ftp teminal.
   
    ftp  <server IP>

    =========================================================================================================================================

--->> HOW TO TRANSFER FILE?
1. go to create file . 
    touch ftp_testfile

2. login user and ftp IP  server.

3. go to transfer file.

    put  ftp_testfile 
4. go any puirticular location fille location.

--->> HOW TO DOWNLOAD FILES SERVER REMOTE.

5. go to give the  server file name and get.

     get  <filename>

    
