---
layout: post
title: 藍牙遙控車
author: [Jacques Wang]
category: [Lecture]
tags: [None]
---

用微控制器製作之藍牙遙控車與演示

---
## Introduction to ESP32 SOCs
**[ESP32]((https://github.com/Jacques3131/MCU-project/blob/main/images/342519029_959060991770867_2036321848111739409_n.jpg?raw=true))**<br>
a dual-core XTensa LX6 MCU, capable of running at 240 MHz with 520 KB of internal SRAM, ntegrated 2.4 GHz, 802.11 b/g/n Wi-Fi and Bluetooth 4.2 (LE) connectivity <br>
**[ESP32-S3](https://www.espressif.com/en/products/socs/esp32-s3)**<br>
a dual-core XTensa LX7 MCU, capable of running at 240 MHz. Apart from its 512 KB of internal SRAM, it also comes with integrated 2.4 GHz, 802.11 b/g/n Wi-Fi and Bluetooth 5 (LE) connectivity that provides long-range support.<br>
**[ESP32-C3](https://www.espressif.com/en/products/socs/esp32-c3)**<br>
a single-core Wi-Fi and Bluetooth 5 (LE) microcontroller SoC, based on the open-source **RISC-V** architecture.<br>

---
### 遙控車系統方塊圖
![](images/342519029_959060991770867_2036321848111739409_n.jpg)

---
## ESP32-WROOM-32
[Insight Into ESP32 Features & Using It With Arduino IDE](https://lastminuteengineers.com/esp32-arduino-ide-tutorial/)<br>

![](https://lastminuteengineers.b-cdn.net/wp-content/uploads/arduino/ESP32-Hardware-Specifications-Reset-Boot-Buttons-LED-Indicators.jpg)

**Features:**<br>
![](https://github.com/rkuo2000/MCU-course/blob/main/images/ESP32_development_board_features.png?raw=true)

---
### NodeMCU-32S pinout
![](https://github.com/rkuo2000/MCU-course/blob/main/images/NodeMCU-32S_pinout.jpg?raw=true)

---
### ESP32-WROOM-32 pinout
![](https://www.mischianti.org/wp-content/uploads/2021/02/ESP32-wroom-32-pinout-mischianti-1024x551.jpg)

---
### ESP32 CAM pinout
![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2019/03/ESP32-CAM-getting-started.jpg?resize=1024%2C576&quality=100&strip=all&ssl=1)
![](https://github.com/rkuo2000/MCU-course/blob/main/images/ESP32-CAM_pinout.jpg?raw=true)
**ESP32-CAM upload code**<br>
![](https://i1.wp.com/randomnerdtutorials.com/wp-content/uploads/2019/12/ESP32-CAM-FTDI-programmer-5V-supply.png?w=750&quality=100&strip=all&ssl=1)
[ESP-WHO (face detection and recognition)](https://github.com/espressif/esp-who)<br>
[ESP32-CAM video streaming face recognition](https://randomnerdtutorials.com/esp32-cam-video-streaming-face-recognition-arduino-ide/)<br>
[ESP32-CAM video streaming Web server](https://randomnerdtutorials.com/esp32-cam-video-streaming-web-server-camera-home-assistant/)<br>
**Code:** [ESP32-CAM Web server](https://github.com/rkuo2000/arduino/tree/master/examples/ESP32CAM_CamWebServer)<br>

---
## EPS32 IDE / Toolchains
[https://github.com/espressif/arduino-esp32/releases/](https://github.com/espressif/arduino-esp32/releases/)<br>

### ESP32 Arduino IDE
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Arduino_IDE_software.png?raw=true)

[【ESP32專欄】如何安裝及設定ESP32的開發環境](https://makerpro.cc/2020/06/how-to-install-and-configure-esp32-development-environment/)<br>

1. Download [Arduino IDE](https://www.arduino.cc/en/Main/Software), then Install on PC
2. Run Arduino
3. Files>Preferences>Setting> URLs = *`https://github.com/espressif/arduino-esp32/releases/download/2.0.5/package_esp32_index.json`*
![](https://makerpro.cc/wp-content/uploads/2020/06/11.png)
4. Tools>Board>Board Managers>ESP32 Arduino> select `NodeMCU-32S`
![](https://makerpro.cc/wp-content/uploads/2020/06/13.png)
5. Tools>Port> select `COM3` or `/dev/ttyUSB0`
![](https://makerpro.cc/wp-content/uploads/2020/06/21.png)
6. Tools>Manager Libraries...> search packages to install
7. Sketch>Include Library>Add .ZIP Library...
8. Download [Sample Codes](https://github.com/rkuo2000/arduino) (click `Code`, then select `Download ZIP`)
9. Uncompress arduino-master.zip, store `samples` folder to *~/Documents/Arduino/*
10. File>Examples> select `01.Basics/Blinky` to `Verify`, then `Upload`
11. Press on IO0 (BOOT) button of NodeMCU-32S to upload code
![](https://makerpro.cc/wp-content/uploads/2020/06/23.png)
![](https://makerpro.cc/wp-content/uploads/2020/06/24.png)
![](https://makerpro.cc/wp-content/uploads/2020/06/25.png)
12. Open Arduino Monitor
![](https://makerpro.cc/wp-content/uploads/2020/06/26.png)

---
### ESP32 Toolchains
**[ESP-IDF](https://github.com/espressif/esp-idf)**<br>
[Standard Setup of Toolchain for Windows](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/windows-setup.html)<br>
1. run [ESP-IDF Installer (556.65MB)](https://dl.espressif.com/dl/esp-idf-tools-setup-2.4.exe)
2. run ESP-IDF Command Prompt / PowerShell
3. run batch
 - `cd C:/Users/USER/Desktop/esp-idf>`
 - `install.bat`
 - `export.bat`
4. run menuconfig 
 - `cd examples/get-started/hello_world`
 - `idf.py set-target ESP32`
 - `idf.py menuconfig`
5. build sample code (hello_world)
 - `cd examples/get-started/hello_world`
 - `idf.py build`
 - `idf.py –p COM3 flash `
 - `idf.py –p COM3 monitor`

**ESP-IDF using Visual Studio Code**<br>
<iframe width="640" height="360" src="https://www.youtube.com/embed/5IuZ-E8Tmhg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

[Standard Toolchain Setup for Linux and macOS](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/linux-macos-setup.html)<br>
1. Install Prerequisites<br>
Ubuntu & Debian:<br> 
`sudo apt-get install git wget flex bison gperf python3 python3-pip python3-setuptools cmake ninja-build ccache libffi-dev libssl-dev dfu-util libusb-1.0-0`<br>
2. Get ESP-IDF<br>
`mkdir -p ~/esp`<br>
`cd ~/esp`<br>
`git clone --recursive https://github.com/espressif/esp-idf.git`<br>
3. Set up the tools<br>
`cd ~/esp/esp-idf`<br>
`./install.sh esp32`<br>
For more chips targets:<br>
`cd ~/esp/esp-idf`<br>
`./install.sh esp32,esp32s2`<br>
`cd ~/esp/esp-idf`<br>
`./install.sh all`<br>
4. Set up the environment variables<br>
`. $HOME/esp/esp-idf/export.sh`<br>

* **Connect Your Device**<br>
Serial ports have the following patterns in their names:<br>
Windows: names like `COM1`<br>
Linux: starting with `/dev/ttyUSB0`<br>
macOS: starting with `/dev/cu`<br>


* **Configure Your Project**<br>
For Windows:<br>
`cd %userprofile%\esp\hello_world`<br>
`idf.py set-target esp32`<br>
`idf.py menuconfig`<br>

Linux/macOS:<br>
`cd ~/esp/esp-idf/examples/get-started/hello_world`<br>
`idf.py set-target esp32`<br>
`idf.py menuconfig`<br>

![](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/_images/project-configuration.png)

* **Build the Project**<br>
`idf.py build`<br>
* **Flash onto the Device**<br>
`idf.py -p PORT [-b BAUD] flash`<br>
* **Monitor the Output**<br>
`idf.py -p <PORT> monitor`<br>
`idf.py -p /dev/ttyUSB0 flash monitor`<br>
* **Erase Flash**<br>
`idf.py -p /dev/ttyUSB0 erase_flash` (need to press IO0 button)<br>

---
## ESP32 Github
### [ESP-ADF](https://github.com/espressif/esp-adf)
![](https://github.com/espressif/esp-adf/raw/master/docs/_static/adf_block_diagram.png)

### [ESP-VA-SDK](https://github.com/espressif/esp-va-sdk)

### [ESP-SkaiNet](https://github.com/espressif/esp-skainet)
![](https://github.com/espressif/esp-skainet/raw/master/img/skainet_overview2.png)

### [ESP-SR](https://github.com/espressif/esp-sr)

---
### Programming ESP32-S
![](https://github.com/rkuo2000/MCU-course/blob/main/images/ESP32-S_programming_with_FT232R.jpg?raw=true)
* Connect ESP32-S to FT232R, FT232R connected to PC<br>
`sudo chmod 777 /dev/ttyUSB0`<br>

* Setup ESP-IDF<br>
`cd ~/esp/esp-idf`<br>
`. ./export.sh`<br>

* A2DP-Sink example code（藍牙音箱）<br>
`cd examples/bluetooth/bluedroid/classic_bt/a2dp_sink`<br>

* menu-configure I2S pins<br>
`idf.py menuconfig`<br>
<br>
`A2DP Example Configuration --->`*press Enter*<br>
```
A2DP Sink Output (External I2S Codec) --->
(22) I2S LRCK (WS) GPIO
(26) I2S BCK GPIO
(25) I2S DATA GPIO
```
*press S to Save*<br>
*press Q to Quit*<br>

* Build code<br>
`idf.py build`<br>

* Upload code to ESP32-S<br>
**press & hold IO0 button, then press & hold RESET button**<br>
`idf.py -p /dev/ttyUSB0 flash`<br>
**release RESET button, then release IO0 button**<br>

---
## ESP32 Projects
### [160+ ESP32 Projects, Tutorials and Guides with Arduino IDE](https://randomnerdtutorials.com/projects-esp32/)

**[小狐狸事務所 - 兩個ESP32 飛控板專案](http://yhhuang1966.blogspot.com/2020/03/esp32-espcopter32.html)**<br>

**[BLE Haptic Dual Joystick Controller](https://create.arduino.cc/projecthub/chuartdo/ble-haptic-dual-joystick-controller-31c2c2)**<br>
<table>
<tr>
<td><img src="https://hackster.imgix.net/uploads/attachments/279661/20170319_173513_KUg6E20Z0b.jpg?auto=compress%2Cformat&w=680&h=510&fit=max"></td>
<td><img src="https://hackster.imgix.net/uploads/attachments/278570/gameproject_s3jiixhwzj_lOA6fZMR5d.JPG?auto=compress%2Cformat&w=680&h=510&fit=max"></td>
</tr>
</table>

**[ESP32-BLE-Gamepad](https://github.com/lemmingDev/ESP32-BLE-Gamepad)**<br>
Sample Code: [ESP32_Gamepad_Test](https://github.com/rkuo2000/arduino/tree/master/examples/ESP32_Gamepad_Test)<br>
Android App: [GamePad Tester Lite](https://play.google.com/store/apps/details?id=gamepadtesterlite.saturday.chimera.com.gamepadtesterlite&hl=en)<br>
![](https://play-lh.googleusercontent.com/4xSp1PlSlrTbVfakY41fdMVM7P8eGG13om4ZPO57FpIrDKLUK0wLKoXukBdNJNCotKU=w240-h480-rw)

<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*

