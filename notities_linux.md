#Notities Linux

#Basic Linux Commands

    mkdir   "map aanmaken"
    touch   "bestand aanmaken"
    vi		  "bestande bewerken"

    useradd "gebruiker aanmaken"
    useradd -m "gebruiker aanmaken met home map"
    groupadd "groep aanmaken"
    groupadd -g	"groep aanmaken met ID"			           voorbeeld: groupadd -g 500 groepnaam

    chown "map/bestand eigenaar wijzigen"                  voorbeeld: chown gebruikersnaam mapnaam
    chgrp "groep eigenaar wijzigen                         voorbeeld: chgrp groepnaam gebruikersnaam
    usermod -aG "gebruiker toevoegen aan een groep"        voorbeeld: usermod -aG groepnaam gebruikersnaam
    gpasswd -d  "gebruiker verwijderen uit de groep"       voorbeeld: gpasswd gebruikersnaam groepnaam
    chmod "bestanden/map rechten wijzigen"	               voorbeeld: chmod 070 mapnaam

    zypper install 'naam van de app'
 
    systemctl start 'naam van een service'    "Services aanzetten
    systemctl stop  'naam van een service' 
    systemctl restart 'naam van een service'
    systemctl enable 'naam van een service'   "Je kan een service permanent aanzetten"

    firewall-cmd --add-service=samba --permanent  "Samba service permanent toevoegen aan firewall zodat de services niet meer geblokkeerd worden"
    firewall-cmd --reload

    uitzondering samba server: 
    setfacl -m g:groupB:r-x /home/samba/Test "Toegang verlenen aan bepaalde groep tot bepaalde map"

    setfacl -m o::--- /home/samba/Test "Geen toegang voor other"
