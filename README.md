# How-to-make-read-only-gsi-become-read-write

Warning : All risks are borne by the user, software damage or the like is not your responsibility.
    
  Condition :     
           # Linux PC/android phone (WSL/Debain based distribution or ubuntu/Arch based distribution, etc.)
           # Downloading read-only or RO GSI For (arm64-bgn/bvn) only


   # This tutorial uses the Termux application, 
    
    
  #  Tutorial :
     #
   1.open the Termux application and run the following command
                  #   termux-setup-storage
                  #   pkg update && pkg upgrade
          
   2.now install the tools in termux and run the following command
                  #   pkg install android-tools e2fsprogs

   3.create a folder in the directory, Example GsiRo
           
   4.extract the Gsi file into GsiRo and change the name of Gsi to system.img
           
   5.Open Termux again and do the following command
                   #   cd /sdcard
                   #   ls
                   #   cd (Enter the file name you created earlier)
                             example: cd GsiRo
                     
   - Note: If your gsi size is not more than 5Gb you have to write 5G, if the size is more than 5Gb you have to change it to 6                    
                #      resize2fs system.img 5G (size will be 5Gb)
                #      e2fsck -E unshare_blocks system.img 
                #      resize2fs -M system.img 
                     
                 Done⚠️
                  
                  
            *And now you can flash system.img into your device*
                  
   #Command flashing gsi rom#.     only infinix hot 20s
            fastboot --disable-verification flash vbmeta (paste vbmeta file)
            fastboot reboot fastboot or reboot fastbootd
            fastboot delete-logical-partition product_a
            fastboot erase system 
            fastboot flash system (Paste the GSI file in .img format)
           
        $ Finally, select reboot to recovery on the Infinix screen and format the data
       
           #and select reboot system
      Done


            
   Credits : @HmmmmmdahlahV (tele) and all developers or admins on Infinix Hot 20s
