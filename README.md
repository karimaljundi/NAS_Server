1. go to Raspberry Pi's imager and download OS Lite for either 64-bit or 32 bit depending on your board You can check if you have a 64-bit or 32-bit by running this command on your board:
   uname -m
2. Make sure you enabled SSH and changed the password to your preference
3. put your SD card into your board
4. Once your board is turned on, you can ssh on your Windows or Mac by running this command on your terminal:
   ssh pi@[ip address]
5. If you do not know your raspberry pi's IP address you should log in to the Raspberry Pi terminal and run the following command:
   ifconfig
   The board's IP address should be the second line followed after "inet"
6. Once you are connected to your Pi via SSH run the following command:
   sudo apt update
   sudo apt upgrade
7. Once the updates are done run this command:
   sudo wget -O - https://raw.githubusercontent.com/OpenMediaVault-Plugin-Developers/installScript/master/install | sudo bash
8. Once that's done the raspberry pi's IP address will change so you need to redo step 5
9. Then go to any web browser enter your pi's IP address and log in with these credentials:
   username: "admin"
   password: "openmediavault"
10. Go to the top right section, click on your profile then change your password and save it.
11. Then plug in a hard drive or a USB stick to your Raspberry Pi board
12. Then go to Storage > Disks and make sure you can see your external disk
13. Then go to Storage > Files System click "mount an existing file system" choose your external storage as a file system click Save and apply changes
14. Then go to Storage > Shared Folders and click "Create" Give it a name, choose your external storage, and click save
15. Then go to Services > NFS > Settings and toggle enable on
16. Go to Services > NFS > Shares then select the shared folder you created and as client, you can type: "192.168.1.0" and click save.
17. Go to Services > SMB and apply the same changes (no need for the client)
18. Apply changes when all of that is done
19. Then go to "This PC" and right-click> "add network location" > next > "Choose a custom network location"
20. Then type in "\[raspberry pi's ip address][Shared Folder's name]
21. Then go back to the openmediavault website go to Users > Users select "pi" change your password and apply changes
22. Then go back to connecting your OS to the NAS and put pi as the username and your new password as the password
23. then give your network a name.
24. Then you are done. CONGRATULATIONS you have successfully connected your Windows/mac to a NAS from your own Raspberry Pi, this can now be used as an alternative to any cloud service you pay for.
