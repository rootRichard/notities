#Update Package Repositories:

    sudo apt update

#Upgrade Installed Packages:

    sudo apt upgrade

#Install Security Updates:

    sudo apt-get dist-upgrade

#Remove Unused Packages:

    sudo apt autoremove

#Install Unattended Upgrades (for automatic updates):

    sudo apt install unattended-upgrades

#Configure Unattended Upgrades:

    sudo dpkg-reconfigure --priority=low unattended-upgrades

#Enable Firewall: // For iptables firewall:

    sudo apt install iptables-persistent
    Follow the prompts to configure the firewall rules.

#For UFW (Uncomplicated Firewall):

    sudo apt install ufw

#Enable the firewall:

    sudo ufw enable

#Secure SSH:

    Edit SSH configuration file:
    sudo nano /etc/ssh/sshd_config

    Disable root login (change PermitRootLogin to no):
    PermitRootLogin no

    Disable password authentication (change PasswordAuthentication to no):
    PasswordAuthentication no

Restart SSH service:

    sudo service ssh restart

Install and Configure Fail2Ban (to prevent brute-force attacks):

    sudo apt install fail2ban

Edit the configuration file:

    sudo nano /etc/fail2ban/jail.local

    Add the following lines:

    [sshd]
    enabled = true
