#NFS server configureren
 
#(Machine1 server) 
   Open konsole
   cd /home
   mkdir nfspublic
   chgrp users nfspublic
   chmod 770 nfspublic
   cd nfspublic
   mkdir map1 map2 map3
   zypper install nfs-kernel-server
   systemctl start nfsserver.service
   systemctl start rpcbind.service
   systemctl stop firewalld.service
   vi /etc/exports
       (voeg de volgende regel in dit bestand en wijzig het ip-adres) 
       /home/nfspublic 192.168.118.0/255.255.255.0(rw,no_root_squash,insecure)  
  
  systemctl restart nfsserver.service
  showmount -e "dit commmando controleert of exports goed geconfigureerd is" 
       Output:
       Export list for localhost.localdomain:
       /home/nfspublic 192.168.118.0/255.255.255.0

#(Machine2 client)
   Open konsole 
   cd /home
   mkdir nfsjevoornaam
   mount -t nfs ip-adres_van_de_server:/home/nfspublic  /home/nfsjevoornaam
