#apache

    zypper refresh
    zypper install apache2
    systemctl start apache2
    systemctl enable apache2
    
    firewall-cmd --zone=public --add-service=http --permanent
    firewall-cmd --reload
    
    systemctl restart apache
