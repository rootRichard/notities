#Open a terminal or SSH into your openSUSE Linux system.

    Create a backup script:
    nano backup_script.sh

#In the editor, enter the following content to create a backup using the rsync command:

    #!/bin/bash
    source_directory="/path/to/source/directory"
    backup_directory="/path/to/backup/directory"
    rsync -av --delete "$source_directory" "$backup_directory"

#Replace /path/to/source/directory with the actual path of the directory you want to back up and /path/to/backup/directory with the path of the backup directory where you want to store the backups.

#Save the file and exit the editor (Ctrl+X, then Y, then Enter).

#Make the script executable:

    chmod +x backup_script.sh

#Edit the crontab file:

    crontab -e

#If prompted to select an editor, choose your preferred one (e.g., nano).

#In the crontab file, add the following line to execute the backup script every 2 minutes:

    */2 * * * * /path/to/backup_script.sh

#Replace /path/to/backup_script.sh with the actual path to the backup script you created in step 2.

#Save the crontab file and exit the editor.
