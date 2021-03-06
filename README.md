<img src="https://raw.githubusercontent.com/HandyMiner/HandyGuide/72303a89968942dc945e05588db5db2a6610c539/logo/cobra.svg" width="150" height="150" />

## HandyMiner-Goldshell GUI

### Download Latest Prebuilt HandyMiner-Goldshell-GUI in [Releases](https://github.com/HandyMiner/HandyMiner-Goldshell-GUI/releases) [Skips all the steps below]

**[Note for Ubuntu users permissions on first run](#ubuntuFirstRun)**

# Easy Installation
       Simple setup will have mining in **seconds** with an incredibly streamlined UX.
       0. Paste your HNS address and create a worker name. 
       1. Select your pool (HNSPool/DXPool/F2Pool support by default) and press Play.
       2. Your miner will immediate connect to the pool and start mining.
       3. Note: Make sure your device is set to not sleep automatically, otherwise your miner will stop mining.
      

### HandyMiner GUI running with the Goldshell HS1 and multiple ASIC devices connected to a USB hub. 
![imgur](https://i.imgur.com/WaWiwWT.jpg)

### HandyBrowser Support Telegram/Handshake Discussion:
[🤝 HandshakeTalk Telegram](http://t.me/HandshakeTalk)

### Donate to the HandyMiner Team:

![alt text](./icons/qr.png)

**HandyMiner Team Donation Address (HNS): ```hs1qwfpd5ukdwdew7tn7vdgtk0luglgckp3klj44f8```**

**HandyMiner Team Donation Address (BTC): ```bc1qk3rk4kgek0hzpgs8qj4yej9j5fs7kcnjk7kuvt```**

### Building from Source

First we will checkout HandyMiner-Goldshell-CLI into the project
```git submodule init```
```git submodule update```

#### Install GUI/CLI-Miner Dependencies:

Node.js is REQUIRED to build AND distribute. **Make sure to get the same version of Node.js as the NW.js version you download contains.** [Download Node.js](https://nodejs.org/)

0. ```npm install -g bower```
1. ```bower install```
2. ```npm install -g node-gyp``` will allow us to compile the native module ```serialport```
3. ```npm install``` in this folder
4. ```mkdir externals```, then copy the node (or nodejs on linux) binary into the externals folder. Make sure this node is the same version as nw.js is running. [Download Node.js binaries here](https://nodejs.org/)

#### Building for Mac

0. [Download NW.js](https://nwjs.io/)
1. Copy this repo to folder ```./nwjs.app/Contents/Resources/app.nw```
2. Copy ./icons/app.icns, ./icons/document.icns to ```./nwjs.app/Contents/Resources/```
3. To change the app display name, follow directions [here](https://nwjs.readthedocs.io/en/latest/For%20Users/Package%20and%20Distribute/)

#### Building for Windows / Linux

0. [Download NW.js](https://nwjs.io/)
1. Checkout this repo into the NW.js directory next to nwjs.exe as a folder named ```package.nw```
2. To change icons, use ResourceHacker to modify nw.exe icons to ./icons/app.ico
3. Further options to build/distribute [here](https://nwjs.readthedocs.io/en/latest/For%20Users/Package%20and%20Distribute/)

### Building native modules
0. (Windows) Install Python 2.7
1. **Make sure your system has the same node.js version as nw.js distributable contains**. This way we can ensure the distributable can run the pre-build native serialport module.
2. npm install in this directory, it will build module ```serialport``` that can run with NW.js

<a id="ubuntuFirstRun" />

### Ubuntu Users First Run Permissions Step:

##### To add your user to the device group for non-sudo device access: 
##### The easy way: ```sudo ./linux_grant_serial_permissions.sh``` in the release root, and then logout/login to the linux machine.

##### Or the less easier way: 

0. Plug in the USB and run the command with the device ID listed in the error, like:
```ls -la /dev/ttyACM0```
It will output something like:
```crw-rw---- 1 root dialout 166, 0 Jul 18 18:06 /dev/ttyACM0```
Which in our case, the group is ```dialout```
1. To add your username to the dialout group:
```sudo useradd -G dialout $USER``` (OR ON SOME SYSTEMS) ```sudo adduser $USER dialout```
2. Now logout/login to the computer and voila, you can now mine without sudo!

##### [LICENSE](https://github.com/HandyMiner/HandyMiner-Goldshell-GUI/blob/master/LICENSE) 

HandyMiner-Goldshell-GUI - A Handshake Mining GUI for the Goldshell HS1 ASIC
    
Copyright (C) 2020 HandyMiner
- Alex Smith - alex.smith@earthlab.tech
- Steven McKie - mckie@amentum.org
- Thomas Costanzo - stanzo89@gmail.com
