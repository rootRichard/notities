#NFS server configureren
 
#Machine1 server 
   1. Open konsole
   2. cd /home
   3. mkdir nfspublic
   4. chgrp users nfspublic
   5. chmod 770 nfspublic
   6. cd nfspublic
   7. mkdir map1 map2 map3
   8. zypper install nfs-kernel-server
   9. systemctl start nfsserver.service
   10. systemctl start rpcbind.service
   11. systemctl stop firewalld.service
   12. vi /etc/exports
       voeg de volgende regel in dit bestand en wijzig het ip-adres 
       /home/nfspublic 192.168.118.0/255.255.255.0(rw,no_root_squash,insecure)  
   13. systemctl restart nfsserver.service
   14. showmount -e "dit commmando controleert of exports goed geconfigureerd is" 
       Output:
       Export list for localhost.localdomain:
       /home/nfspublic 192.168.118.0/255.255.255.0

#Machine2 client
   1. Open konsole 
   2. cd /home
   3. mkdir nfsjevoornaam
   4. mount -t nfs ip-adres_van_de_server:/home/nfspublic  /home/nfsjevoornaam
