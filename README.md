# Patch fix brightness and AppleHDA patched for Dell Latitude E6540

How to install?
+ Update A21 BIOS version <a href="https://www.dell.com/support/home/vn/en/vnbsdt1/Drivers/DriversDetails?driverId=Y5FNT">here</a> // Unnecessary. Fixed for all BIOS version 
+ After install macOS, download my patch and put it in Library/Extensions (L/E)
+ Open terminal and run these command to rebuild kextcache

      sudo chmod -Rf 755 /L*/E*
      sudo chown -Rf 0:0 /L*/E*
      sudo touch -f /L*/E*
      sudo chmod -Rf 755 /S*/L*/E*
      sudo chown -Rf 0:0 /S*/L*/E*
      sudo touch -f /S*/L*/E*
      sudo kextcache -Boot -U /

+ After rebuild kextcache, run this command to disable hibernation (Make sure to disable hibernation as it's a prerequisite to get sleep & wake to work on a Hackintosh)

      sudo pmset hibernatemode 3
      sudo rm -f /var/vm/sleepimage

+ Restart and enjoy
