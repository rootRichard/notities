#Samba

!!!(Configureren met root account)

#Machine1 Linux

    open konsole
    inloggen met root account "su"  enter en daarna wachtwoord van root
    cd /home
    maak een map aan "mkdir smbjevoornaam"
    chgrp users smbjevoornaam
    chmod 770 smbjevoornaam "om de rechten van de groep eigenaar te wijzigen
    vi /etc/samba/smb.conf
       helemaal onderaan voeg de volgende regels

       [smbjevoornaam]
                        path = /home/smbjevoornaam
                        writeable = yes
                        comment = "Het is optioneel"
        
       als je klaar bent, druk op ESC daarna :wq!

    systemctl start smb.service
    systemctl start nmb.service
    systemctl stop firewalld.service
    smbpasswd -a "gebruikersnaam" (smbpasswd -a student)
    ip a "kopieer het ip-adres van Linux machine"

 

#Machine2 Windows client

Maak een netwerk verbinding
    path \\ip-adres_van_de_server\smbjevoornaam
    
    Opnieuw verbinding maken... "uitvinken"
    Verbinding maken met nieuwe referenties "aanvinken"
    Het wordt een nieuwe venster geopend met de smb map
