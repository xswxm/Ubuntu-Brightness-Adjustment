Ubuntu-Brightness-Adjustment


------ Setting Up ------
1. Edit the script
   The existing file locations are for Asus ux303 running Ubuntu 16.04 so you may have to replace the path to yours.

2. Move file to /usr/local/bin
   sudo mv Downloads/brightness /usr/local/bin

3. Set persmission and user group to root
   sudo chmod 755 /usr/local/bin/brightness
   sudo chown root:root /usr/local/bin/brightness

4. Add exceptions for the script so it can run without asking for entering password
   sudo visudo
    - Navigate to the last line and add a line as listed below (Replace the USERNAME with your username)
      USERNAME ALL=(root) NOPASSWD: /usr/local/bin/brightness
    - Save it and you are ready to go

------ How to Use ------
Open System Settings - Keyboard - Shortcuts and add your commands
Example commands:
1. Set the the value keyboard brightness to 0
   sudo brightness -k -set 0
2. Increase keyboard brightness by 1
   sudo brightness -k -inc 1
3. Decrease keyboard brightness by 1
   sudo brightness -k -dec 1
4. Set the the value screen brightness to 200
   sudo brightness -d -set 200
5. Increase screen brightness by 100
   sudo brightness -d -inc 100
6. Decrease screen brightness by 100
   sudo brightness -d -dec 100
