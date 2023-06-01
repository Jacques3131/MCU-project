---
layout: post
title: 血氧機
author: [Jacques Wang]
category: [Lecture]
tags: [jekyll, ai]
---

利用ESP32與感測器、顯示屏測量血氧
<iframe width="347" height="618" src="https://www.youtube.com/embed/NCO14Flf9SI" title="2023年6月1日" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---
## [Basic Guide to IoT Wireless Protocol Standards & Comparison](https://www.keysecurity.com.tw/guide-to-iot-wireless-protocol-standards.html?lang=en)
![](https://www.keysecurity.com.tw/guide-to-iot-wireless-protocol-standards.jpg)

---
## [Introduction to Bluetooth (BT)](https://www.gsmfavorites.com/documents/bluetooth/introduction/)
Bluetooth is an always-on, short-range radio hookup that resides on a microchip. It was initially developed by Swedish mobile phone maker Ericsson in 1994 as a way to let laptop computers make calls over a mobile phone.<br>

The Bluetooth standards are published by an industry consortium known as the Bluetooth SIG (special interest group).<br>

The concept behind Bluetooth is to provide a universal short-range wireless capability. Using the 2.4 GHz band, available globally for unlicensed low-power uses, two Bluetooth devices within 10 m of each other can share up to 720 Kbps of capacity. <br>

---
### [Protocol Architecture](http://junyelee.blogspot.com/2019/10/bluetooth-in-linux.html)
![](https://1.bp.blogspot.com/-uj1y2SYPYMs/XukxCVJcSHI/AAAAAAAAF9Y/N_4Ab0mZDPwNaEOfP707QKJWZzW4JviRQCK4BGAsYHg/w625-h514/BT-Stack.gif)
![](https://1.bp.blogspot.com/-rowGi1DXVAU/XulnfvD8OjI/AAAAAAAAF-Q/ShusVGQUvgEdA0p1KbqW909iYwRYDhdiwCK4BGAsYHg/w500-h323/btbd.jpg)
Bluetooth is defined as a layered protocol architecture consisting of core protocols, cable replacement and telephony control protocols, and adopted protocols.<br>
The core protocols form a five-layer stack consisting of the following elements:<br>
* **Radio** - Specifies details of the air interface, including frequency, the use of frequency hopping, modulation scheme, and transmit power.
* **Baseband** - Concerned with connection establishment within a piconet, addressing, packet format, timing, and power control.
* **Link manager protocol (LMP)** - Responsible for link setup between Bluetooth devices and ongoing link management. This includes security aspects such as authentication and encryption, plus the control and negotiation of baseband packet sizes.
* **Logical link control and adaptation protocol (L2CAP)** - Adapts upper-layer protocols to the baseband layer. L2CAP provides both connectionless and connection-oriented services.
* **Service discovery protocol (SDP)** - Device information, services, and the characteristics of the services can be queried to enable the establishment of a connection between two or more Bluetooth devices.

---
### [Host Controller Interface (HCI)](https://www.amd.e-technik.uni-rostock.de/ma/gol/lectures/wirlec/bluetooth_info/hci.html)
The HCI provides a command interface to the baseband controller and link manager, and access to hardware status and control registers. Essentially this interface provides a uniform method of accessing the Bluetooth baseband capabilities.The HCI exists across 3 sections, the Host - Transport Layer - Host Controller. Each of the sections has a different role to play in the HCI system.
Bluetooth-defined Host Controller Transport Layers: **UART(H4)**, **USB**, **SPI**, **H3/RS232**.<br>

---
### RFCOMM
RFCOMM is the cable replacement protocol included in the Bluetooth specification.<br>
Serial ports are one of the most common types of communications interfaces used with computing and communications devices. Hence, RFCOMM enables the replacement of serial port cables with the minimum of modification of existing devices. RFCOMM provides for binary data transport and emulates EIA-232 control signals over the Bluetooth baseband layer. EIA-232 (formerly known as RS-232) is a widely used serial port interface standard.

---
### TCS BIN
Bluetooth specifies a telephony control protocol. TCS BIN (telephony control specification binary) is a bit-oriented protocol that defines the call control signaling for the establishment of speech and data calls between Bluetooth devices. In addition, it defines mobility-management procedures for handling groups of Bluetooth TCS devices.

---
### Adopted Protocols
The adopted protocols are defined in specifications issued by other standards-making organizations and incorporated into the overall Bluetooth architecture. The Bluetooth strategy is to invent only necessary protocols and use existing standards whenever possible.<br>
These are the adopted protocols:<br>
* PPP - The point-to-point protocol is an Internet standard protocol for transporting IP datagrams over a point-to-point link;
* TCP/UDP/IP - These are the foundation protocols of the TCP/IP protocol suite;
* OBEX - The object exchange protocol is a session-level protocol developed by the Infrared Data Association (IrDA) for the exchange of objects. OBEX provides functionality similar to that of HTTP, but in a simpler fashion. It also provides a model for representing objects and operations. Examples of content formats transferred by OBEX are vCard and vCalendar, which provide the format of an electronic business card and personal calendar entries and scheduling information, respectively;
* WAE/WAP - Bluetooth incorporates the wireless application environment and the wireless application protocol into its architecture.

---
### Usage Models
* **File transfer** - The file transfer usage model supports the transfer of directories, files, documents, images, and streaming media formats. This usage model also includes the capability to browse folders on a remote device;
* **Internet bridge** - With this usage model, a PC is wirelessly connected to a mobile phone or cordless modem to provide dial-up networking and fax capabilities. For dial-up networking, AT commands are used to control the mobile phone or modem, and another protocol stack (such as PPP over RFCOMM) is used for data transfer. For fax transfer, the fax software operates directly over RFCOMM;
* **LAN access** - This usage model enables devices on a piconet to access a LAN. Once connected, a device functions as if it were directly connected (wired) to the LAN;
* **Synchronization** - This model provides a device-to-device synchronization of PIM (personal information management) information, such as phone book, calendar, message, and note information. IrMC (Ir mobile communications) is an IrDA protocol that provides client/server capability for transferring updated PIM information from one device to another;
* **Three-in-one phone** - Telephone handsets that implement this usage model may act as a cordless phone connecting to a voice base station, as an intercom device for connecting to other telephones, and as a cellular phone;
* **Headset** - The headset can act as a remote device's audio input and output interface.

---
## [Introduction to Bluetooth Low Energy (BLE)](https://www.argenox.com/library/bluetooth-low-energy/introduction-to-bluetooth-low-energy-v4-0/)
Bluetooth Low Energy, also called BLE, was introduced in 2010 and ushred in a new age of connectivity, especially between smart devices and smartphones. BLE is a new wireless protocol that shares some features with Bluetooth Classic.

![](https://github.com/rkuo2000/MCU-course/blob/main/images/BT_wireless_protocol_comparison.png?raw=true)

---
### BLE Protocol Stack
![](https://miro.medium.com/max/1400/1*7R_hkwuk8v7gClsVXtoqPw.png)

---
## ESP32 BT & BLE

### ESP32 Classic Bluetooth Serial communication
* begin()
* available()
* write()
* read()

---
### Examples>BluetoothSerial>SerialToSerialBT
* Modify SerialBT.begin("ESP32test"); to "ESP32-yourname"
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Examples_BluetoothSerial_SerialToSerialBT.png?raw=true)
* Download [Serial Bluetooth Terminal App](https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal&hl=en&gl=US) to your smartphone
![](https://github.com/rkuo2000/MCU-course/blob/main/images/APP_Serial_Bluetooh_Terminal.png?raw=true)
* Setting Bluetooth Paring your phone with the device named ESP32test
* Open BT terminal APP to select the device named ESP32test to connect
* Keyin to send text to ESP32

---
### [Homework]: ESP32_BTserial.ino
```
#include <BluetoothSerial.h>

BluetoothSerial SerialBT;

char BTbuf[255];

void setup() {
  Serial.begin(115200);  
  SerialBT.begin("ESP32BT"); //Bluetooth device name
  Serial.println("The device started, now you can pair it with bluetooth!");
}

void loop() { 
  uint8_t i, buflen;

  i=0;
  while (SerialBT.available()) {
      BTbuf[i]=SerialBT.read();
      i++;
  }
  buflen = i;
  for (i=0; i<buflen; i++) {
	  Serial.write(BTbuf[i]);
  }
}
```
* use [Serial Bluetooth Terminal App](https://play.google.com/store/apps/details?id=de.kai_morich.serial_bluetooth_terminal&hl=en&gl=US) to send text to ESP32
* use **[BT2RC](https://github.com/rkuo2000/MCU-course/blob/main/files/BT2RC.aia)** APP to send command to ESP32
* check message sent from APP displayed on serial-monitor

---
### Examples>ESP32 BLE Arduino>BLE_uart
* Modify BLEDevice::init("UART Service") to "UART-yourname"
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Examples_BLE_uart.png?raw=true)
* Using **[BLE2RC](https://github.com/rkuo2000/MCU-course/blob/main/files/BLE2RC.aia)** to send commands to ESP32_BLE_uart
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Examples_BLE_uart_monitor.png?raw=true)

---
### [Homework]: Sketch>ESP32_RoboCar_BLE
* Download [ESP32_RoboCar_BLE](https://github.com/rkuo2000/arduino/blob/master/examples/ESP32_RoboCar_BLE/ESP32_RoboCar_BLE.ino)
* Modify BLEDevice::init("ESP32-UART") to "UART-yourname"
* use **[BLE2RC](https://github.com/rkuo2000/MCU-course/blob/main/files/BLE2RC.aia)** APP to send commands to ESP32 running ESP32_RoboCar_BLE.ino

---
### Examples>ESP32 BLE Arduino>BLE_iBeacon
* Modify BLEDevice::init("UART Service") to "UART-yourname"
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Examples_BLE_iBeacon.png?raw=true)

---
## Arduino Library: ESP32-BLE-Gamepad
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Arduino_Library_ESP32-BLE-Gamepad.png?raw=true)
* BleConnectionStatus.h
* BleConnectionStatus.cpp
* BleGamepad.h
* BleGamepad.cpp

---
### ESP32-BLE-Gamepad examples
* DrivingControllerTest.ino
* FlightControllerTest.ino
* Gamepad.ino
* IndividualAxes.ino
* Keypad4x4.ino
* MultipleButtonsAndHats.ino
* MultipleButtonsDebounce.ino
* PotAsAxis.ino
* SingleButton.ino
* SingleButtonDebounce.ino
* TestAll.ino

---
## Arduino Library> ESP32 BLE mouse
[ESP32 BLE Mouse Library](https://github.com/T-vK/ESP32-BLE-Mouse)<br>

### Examples> ESP32 BLE mouse> MouseButton
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Example_ESP32_MPU6050.jpg?raw=true)
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Examples_ESP32_BLE_mouse_MouseButton.png?raw=true)

---
### Sketch>ESP32_BLEmouse_MPU6050.ino
[ESP32_BLEmouse_MPU6050.ino](https://github.com/rkuo2000/arduino/blob/master/examples/ESP32/ESP32_BLEmouse_MPU6050/ESP32_BLEmouse_MPU6050.ino)
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Sketch_ESP32_BLEmouse_MPU6050.png?raw=true)
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Sketch_ESP32_BLEmouse_MPU6050_monitor.png?raw=true)

---
### [Homework]: ESP32_BLEmouse_MPU6050ypr.ino 
* using IMU (MPU6050_DMP) pitch & roll to control Mouse cursor movement

---
## [ESP-IDF Bluetooth examples](https://github.com/espressif/esp-idf/tree/master/examples/bluetooth)
* bluedroid
* blufi
* esp_ble_mesh
* esp_hid_device
* esp_hid_host
* hci
* nimble

---
### ESP-IDF BlueDroid examples
The following is a list of Classic Bluetooth Profiles and Protocols supported by BLUEDROID Bluetooth Stack of ESP32.

**Classic Bluetooth Profiles**<br>
* [GAP](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/bluetooth/esp_gap_bt.html)
* [A2DP (SNK)](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/bluetooth/esp_a2dp.html)
* [AVRCP (CT)](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/bluetooth/esp_avrc.html)
* [SPP](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/api-reference/bluetooth/esp_spp.html)
  - bluetooth/bluedroid/classic_bt/bt_spp_acceptor
  - bluetooth/bluedroid/classic_bt/bt_spp_initiator
  - *This is a SPP demo. This demo can discover the service, connect, send and recive SPP data*
  
**Classic Bluetooth Protocols**<br>
* L2CAP
* SDP
* AVDTP
* AVCTP

---
### ESP32 BLE examples
**~/esp/esp-idf/examples/bluetooth/bluedroid/ble**
* ble_ancs
* ble_compatibility_test
* ble_eddystone
* ble_hid_device_demo
* ble_ibeacon
* ble_spp_client
* ble_spp_server
* ble_throughput
* gatt_client
* gatt_multi_connect
* gatt_security_client
* gatt_security_server
* gatt_server
* gatt_server_service_table

---
### ESP32 BLE5.0 examples
**~/esp/esp-idf/examples/bluetooth/bluedroid/ble50**
* ble50_security_client
* ble50_security_server
* multi-adv
* peroidic-adv
* peroidic-async

---
### ESP32 A2DP/SPP/HFP examples
**~/esp/esp-idf/examples/bluetooth/bluedroid/classic_bt**
* a2dp_sink
* a2dp_source
* bt_discrovery
* bt_hid_mouse_device
* bt_spp_acceptor
* bt_spp_initiator
* bt_spp_vfs_acceptor
* bt_spp_vfs_initiator
* hfp_ag
* hfp_hf

---
### ESP32 Coex examples
**~/esp/esp-idf/examples/bluetooth/bluedroid/coex**
* a2dp_gatts_coex
* gattc_gatts_coex

---
## 室內定位

目前室內定位常用的定位方法，從原理上主要分為七種：<br>
1. **鄰近探測法:** 
適合於一些對定位精度要求不高的應用，例如自動識別系統用於公司的員工簽到。 

2. **質心定位法:**
被偵測移動設備內放置多個信標（beacon），計算其信標質心坐標作為移動設備的坐標。 

3. **多邊定位法:**
通過測量待測目標到已知參考點之間的距離，從而確定待測目標的位置。例如:車隊追蹤

4. **三角定位法:**
三角定位方法是在獲取待測目標，相對3個已知基站參間的距離，可以確定唯一的三角形，即可確定待測目標的位置。精度高、應用廣。

5. **極點法:**
通過測量相對某一已知參考點的距離和角度從而確定待測點的位置，在大地測量中得到廣泛應用。

6. **指紋定位法:**
在定位空間中建立指紋資料庫，通過將實際信息與資料庫中的參數進行對比來實現定位。不適合環境變化較大的場景。 

7. **航位推算法:**
是在已知上一位置的基礎上，通過計算或已知的運動速度和時間計算得到當前的位置。

---
### [室內定位技術](https://www.atc-tech.com.tw/%E5%BA%B7%E8%81%AF%E7%9A%84%E7%B6%93%E9%A9%97/%E8%97%8D%E8%8A%BD%E5%AE%A4%E5%85%A7%E5%AE%9A%E4%BD%8D?q=%E8%97%8D%E8%8A%BD%E5%AE%A4%E5%85%A7%E5%AE%9A%E4%BD%8D)
對於目前流行的高精度室內定位技術主要有，藍牙定位技術，超寬頻uwb定位技術，RFID定位技術，WLAN定位技術

* 藍牙定位技術
藍牙技術通過測量信號強度進行定位。這是一種短距離低功耗的無線傳輸技術，在室內安裝適當的藍牙基站，就可以獲得待測物體的位置信息。藍牙室內定位技術最大的優點是設備體積小、因此很容易推廣普及。理論上，對於持有集成了藍牙功能移動終端設備，只要室內定位設備的藍牙功能開啟，藍牙室內定位系統就能夠對其進行位置判斷。

* 超寬頻uwb定位技術
超寬頻技術是近年來新興的一項無線技術，目前，包括美國，日本，加拿大等在內的國家都在研究這項技術，在無線室內定位領域具有良好的前景。UWB技術是一種傳輸速率高(最高可達1000Mbps以上)，發射功率較低，穿透能力較強並且是基於極窄脈衝的無線技術，無載波。正是這些優點，使它在室內定位領域得到了較為精確的結果。

* RFID定位技術
射頻識別技術（RFID），射頻定位技術實現起來非常方便，而且系統受環境的干擾較小，電子標籤信息可以編輯改寫比較靈活。射頻識別技術利用射頻方式進行非接觸式雙向通信交換數據以達到識別和定位的目的。這種技術作用距離短，成本較低。

* WLAN定位技術
室內定位解決方案是Wi-Fi。在無線區域網中測得無線信號的強度，利用信號強度的方法進行定位。

---
### [藍牙室內定位](https://www.masters.tw/226204/indoor-positioning)
藍牙定位技術是利用在室內安裝的若干個藍牙信標（Beacon/iBeacon）當作微定位訊號發射器來建立網絡，由於傳輸距離的不同會有不同程度的訊號衰減，接收端收到藍牙訊號後即可計算出接收端與各信標的距離，套用三角定位算法即能獲得手機在此區域內的位置。
![](https://www.2cm.com.tw/upload/news/N180205002720180205110514.png)
<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


