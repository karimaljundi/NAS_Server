# NAS_Server
1. go to raspberry pi's imager and download OS Lite for either 64 bit or 32 bit depending on your board
   You can check if you are have a 64 bit or 32 bit by running this command on your board:
     uname -m
2. Make sure you enabled ssh and changed the password to your preference
3. put your sd card into your board
4. Once your board is turned on, you can ssh on your windows or mac by running this command on your terminal: ssh pi@[ip address]
5. If you do not know your rapberry pi's ip address you should login to the raspberry pi terminal and run the following command:
    ifconfig
   The board's ip address should be the second line followed after "inet"
6. Once you are connected to your pi via ssh run the following command:
     sudo apt update
    sudo apt upgrade
7. Once  the updates are done run this command:
     sudo wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash
8. Once that's done the raspberry pi's ip address will change so you need to redo step 5
9. then go to any web browser and enter your pi's ip address and login with these credentials:
   username: "admin"
   password: "openmediavault"
10. Go to the top right section, click on your profile,m then change password and save it.
11. Then plug in a hard drive or a usb stick to your raspberry pi board
12. Then go to Storage > Disks and make sure you can see your external disk
13. Then go to Storage > Files System then click "mount an existing file system" and choose your external storage as a file system and click save and apply changes
14. Then go to Storage > Shared Folders and click "Create" give it a name, choose your external storage and click save
15. Then go to Services > NFS > Settings and toggle enable on
16. Go to Services > NFS > Shares then select the shared folder you created and as client you can type: "192.168.1.0" and click save.
17. Go to Services > SMB and apply the same changes (no need for client)
18. Apply changes when all of that is done
19. Then go "This PC" and right click > "add network location" > next > "Choose a custom network location"
20. Then type in "\\[raspberry pi's ip address]\[Shared Folder's name]
21. Then go back to the openmediavault website and go to Users > Users and select "pi" and change your password and apply changes
22. Then go back to connecting your OS to the NAS and put pi as the username and your new password as the password
23. then give your network a name.
24. Then you are done. CONGRATULATIONS you have successfully connected yyour windows/mac to a NAS from your own raspberry pi, this can now be used as an alternative to any cloud service you pay for.
