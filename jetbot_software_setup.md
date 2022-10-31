# JetBot Software Setup
- Video Instruction: https://youtu.be/6I9ZT5NKmsA
- Official Instruction: https://jetbot.org/master/software_setup/sd_card.html
- Note that following instruction includes some important processes that are not included above.

## 1. Flash JetBot SD Card Image
1. Download JetBot SD card image for Jetson Nano 4GB from [here](https://drive.google.com/file/d/1o08RPDRZuDloP_o76tCoSngvq1CVuCDh/view?usp=sharing).
2. Download balenaEtcher from [here](https://www.balena.io/etcher/) and install it to your PC.
3. Instert an empty micro SD card into your PC.
4. Flash JetBot SD card image ```jetbot-043_nano-4gb-jp45.zip``` onto the micro SD card with balenaEtcher.

## 2. First Boot and WiFi Setup
1. Insert the micro SD card into the JetBot.
2. Plug an HDMI display and a USB keyboard to the JetBot.
3. Turn on the JetBot power switch to boot.
4. Login with the username ```jetbot``` and the password ```jetbot```.
5. Check available WiFi by the command ```sudo nmcli device wifi list``` with the password ```jetbot```.
6. Connect to one of the available WiFi by the command ```sudo nmcli device wifi connect <WiFi SSID> password <WiFi PASSWORD>```
7. Shutdown the JetBot by the command ```sudo shutdown now```.
8. Turn off the JetBot power switch.
9. Unplug the HDMI display and the USB keyboard. From next time, you don't have to use the display and the keyboard anymore.

## 3. Remote Access and Additional Setup
### Access to the JetBot via Web Browser
1. Boot the JetBot. Wait for the JetBot to be connected to the WiFi.
2. Check the IP address shown on the JetBot display.
3. Make sure your computer is connected to the same WiFi with your JetBot.
4. Open an web browser and access to ```http://<JETBOT_IP_ADDRESS>:8888```, e.g. ```http://192.168.10.2:8888```.
5. Login to the JetBot with the password ```jetbot```.

### Install SSH and Expand Disk Space
1. Open the Terminal from the Launcher.
2. Update apt by the command ```apt update```.
3. Install SSH by the command ```apt install ssh -y```.
4. Login via SSH by the command ```ssh jetbot@0.0.0.0``` then type ```yes``` and password ```jetbot```.
5. Expand the diskspace by the commands,
    ```
    cd jetcard
    git pull
    ./scripts/jetson_install_nvresizefs_service.sh
    ```
1. Reboot the JetBot by the command ```sudo reboot now```.

## 4. Regular Shutdown
After finishing above setups, you can shutdown your JetBot from the terminal via web browser.
1. If needed, open a terminal from the Launcher.
1. Login via SSH by the command ```ssh jetbot@0.0.0.0``` then type ```yes``` and password ```jetbot```.
2. Shutdown by the command ```sudo shutdown now``` with the password ```jetbot```.
