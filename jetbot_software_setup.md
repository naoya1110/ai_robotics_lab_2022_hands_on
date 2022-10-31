# JetBot Software Setup

## Flash JetBot SD card image
1. Download JetBot SD card image from [here](https://drive.google.com/file/d/1o08RPDRZuDloP_o76tCoSngvq1CVuCDh/view?usp=sharing).
2. Download balenaEtcher from [here](https://www.balena.io/etcher/) and install it to your PC.
3. Instert an empty micro SD card into your PC.
4. Flash JetBot SD card image ```jetbot-043_nano-4gb-jp45.zip``` to the micro SD card with balenaEtcher.

## First Boot and WiFi setup
1. Insret the micro SD card into the JetBot.
2. Plug an HDMI display and a usb keybord to the JetBot.
3. Boot the JetBot.
4. Login with the username ```jetbot``` and the password ```jetbot```.
5. Check available WiFi by the command ```sudo nmcli device wifi list``` with the password ```jetbot```.
6. Connect to one of the available WiFi network by the command ```sudo nmcli device wifi connect <WiFi SSID> password <PASSWORD>```
