# Ubuntu Brightness Adjustment
It is a bash script for adjusting brightness for both your keyboard and screen.

### Setting Up
Edit the script. The existing file locations are for Asus ux303 running Ubuntu 16.04 so you may have to replace the path to yours.
```sh
if [ $1 == '-k' ]; then
    path="/sys/devices/platform/asus-nb-wmi/leds/asus::kbd_backlight/"
elif [ $1 == '-d' ]; then
    path="/sys/class/backlight/intel_backlight/"
else
    exit
fi
```
Move file to /usr/local/bin
```sh
sudo mv YourDownloadedFileFolder/brightness /usr/local/bin
```
Set persmission and user group to root
```sh
sudo chmod 755 /usr/local/bin/brightness
sudo chown root:root /usr/local/bin/brightness
```
Add exceptions for the script so it can run without asking for entering password
```sh
sudo visudo
```
Navigate to the last line and add a line as listed below (Replace the USERNAME with your username)
```sh
USERNAME ALL=(root) NOPASSWD: /usr/local/bin/brightness
```
Save it and you are ready to go

### How to Use
Open System Settings - Keyboard - Shortcuts and add your commands
```sh
# Example commands
# Set the the value keyboard brightness to 0
sudo brightness -k -set 0
# Increase keyboard brightness by 1
sudo brightness -k -inc 1
# Decrease keyboard brightness by 1
sudo brightness -k -dec 1
# Set the the value screen brightness to 200
sudo brightness -d -set 200
# Increase screen brightness by 100
sudo brightness -d -inc 100
# Decrease screen brightness by 100
sudo brightness -d -dec 100
```
License
----
MIT
