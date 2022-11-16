# JetBot Software Setup
- Video Instruction: https://youtu.be/6I9ZT5NKmsA
- Official Instruction: https://jetbot.org/master/software_setup/sd_card.html
- You need a PC, an HDMI display and a USB keyboard to setup.
- We recommend you to follow the instruction below it includes some updates that are not included above.

## 1. Flash JetBot SD Card Image
1. Download JetBot SD card image for Jetson Nano 4GB ```jetbot-043_nano-4gb-jp45.zip``` from [here](https://jetbot.org/master/software_setup/sd_card.html).

    <img src="imgs/get_sd_card_image.jpg" width="400">

3. Download balenaEtcher from [here](https://www.balena.io/etcher/) and install it to your PC.

    <img src="imgs/download_etcher.jpg" width="300">    

4. Instert an empty micro SD card into your PC.
5. Flash the JetBot SD card image ```jetbot-043_nano-4gb-jp45.zip``` onto the micro SD card using balenaEtcher.
    
    <img src="imgs/etcher.jpg" width="400">

## 2. First Boot and WiFi Setup
1. Insert the micro SD card into the JetBot.

    <img src="imgs/insert_sd_card.jpg" width="300">

2. Plug an HDMI display and a USB keyboard to the JetBot.
3. Turn on the JetBot power switch to boot.

    <img src="imgs/jetbot_power_switch.jpg" width="300">

4. Login with the username ```jetbot``` and the password ```jetbot```.

    <img src="imgs/login_first_boot.jpg" width="250">

5. Check available WiFi by the command ```sudo nmcli device wifi list``` with the password ```jetbot```.

    <img src="imgs/check_available_wifi.jpg" width="450">

6. Connect to one of the available WiFi by the command ```sudo nmcli device wifi connect <WiFi_SSID> password <WiFi_PASSWORD>```

    <img src="imgs/connect_wifi.jpg" width="800">

7. Shutdown the JetBot by the command ```sudo shutdown now```.
8. Turn off the JetBot power switch.
9. Unplug the HDMI display and the USB keyboard from the JetBot. From next time, you don't need the display and the keyboard anymore.

## 3. Remote Access and Additional Setups
### Access to the JetBot via Web Browser
1. Boot the JetBot. Wait for the JetBot to be connected to the WiFi automatically.
2. Check the IP address shown on the JetBot display.

    <img src="imgs/ip_on_oled.jpg" width="300">

3. Make sure your computer is connected to the same WiFi with your JetBot.
4. Open a web browser and access to ```http://<JETBOT_IP_ADDRESS>:8888```, e.g. ```http://192.168.11.11:8888```.

    <img src="imgs/ip_in_browser.jpg" width="300">

5. Login to the JetBot with the password ```jetbot```.

    <img src="imgs/login_via_browser.jpg" width="400">

### Install SSH and Reconfigure Partition
1. Open the Terminal from the Launcher.

    <img src="imgs/start_terminal.jpg" width="400">

2. Update APT by the command ```apt update```.

    <img src="imgs/apt_update.jpg" width="335">

3. Install SSH by the command ```apt install ssh -y```.

    <img src="imgs/apt_install_ssh.jpg" width="400">


4. Login via SSH by the command ```ssh jetbot@0.0.0.0``` then type ```yes``` and password ```jetbot```.

    <img src="imgs/ssh_jetbot.jpg" width="400">

5. Reconfigure the partition by the commands,
    ```
    cd jetcard
    git pull
    ./scripts/jetson_install_nvresizefs_service.sh
    ```
1. Shutdown the JetBot by the command ```sudo shutdown now```.

1. Boot the JetBot again. Now you have more free space in your disk.

    <img src="imgs/more_free_disk.jpg" width="300">

## 4. Regular Shutdown
After finishing above setups, you can shutdown your JetBot from the terminal via the web browser.
1. If needed, open a terminal from the Launcher.
1. Login via SSH by the command ```ssh jetbot@0.0.0.0``` then type ```yes``` and password ```jetbot```.
2. Shutdown the JetBot by the command ```sudo shutdown now``` with the password ```jetbot```.
