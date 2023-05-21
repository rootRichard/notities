#smb services toevoegen aan firewall

    firewall-cmd --add-service=samba --permanent    
    firewall-cmd --reload
 

#NFS services toevoegen aan firewall

    firewall-cmd --add-service=nfs --permanent    
    firewall-cmd --reload
