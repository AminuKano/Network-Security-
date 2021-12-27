
## Kali Linux
* Kali is a free Debian-based Linux OS, most famous for its use in penetration testing and security auditing. Containing hundreds of useful pre-installed tools, of which some will be used throughout this workshop.

* You should have received a USB drive containing an installed copy of Kali Linux, plug it in and launch your device from USB. See [this link](https://www.acronis.com/en-gb/articles/usb-boot/) for a guide on how to launch your device from USB.  

* In the case that your system is not automatically prioritising the USB on boot up, you will have to open the BIOS or the boot manager and manually select the USB. 

* The keys to enter the boot order settings are different for every device, but the most common ones are DEL, F1, F2, F12. Eventually, if your screen looks like the screenshot below then you are ready to continue to the next step.

* Kali Linux should have some scripts included in the root directory; they will be useful throughout the tutorial (~/cybersecurity-resources/).

*   Otherwise, open the terminal in the Kali machine and git clone the scripts into your directory using the following command. 

**_git clone https://github.com/ysj-HIoT/cybersecurity-resources_**

## WiFi Pineapple
* Users looking for a free network in public spaces could easily be fooled with a simple SSID, to believe that the network is managed by a legitimate organisation. 

* Wi-Fi Pineapple is a networking device developed by Hak5, its main function is to audit and broadcast a wireless connection. However, it is also designed for scenarios where the broadcasted network acts as a honeypot for public clients. 

* Using the Wi-Fi Pineapple, it’s possible to monitor the network connections (the device acts as a man in the middle). 

* With Wi-Fi Pineapple hackers uses landing page to manipulate the connected users into providing their details into a fake website.

* During this session you will practice the use of this device and learn about its security breach potential. You will also be introduced to certain methods on the internet that can further protect yourself from eavesdropping devices like this.

## setting up WiFi Pineapple

* Connect your WiFi Pineapple nano into a USB port on your Linux system, if you are using a virtual machine, make sure that your system can see the USB connections. Use lsusb to check this

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_1.PNG)

* ASIX Electronics Corp. is the device that you are looking for, if you are struggling to find it you use [this guide.](https://www.techrepublic.com/article/how-to-enable-usb-in-virtualbox/)

* The WiFi Pineapple should have now set up an adapter on your machine as well, confirm this, open the terminal and type the following command:

_ifconfig_ 

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_2.PNG)

* Next, disconnect the Pineapple Nano, then type the following command in the terminal
* 
*   _wget wifipineapple.com/wp6.sh_ 
*   
* The command should download the wp6.sh file into your current directory. This file is responsible for setting up your Wifi Pineapple. 
* To be able to use the wp6.sh, type the folliwng command as indicated in the Figure below:

 _chmod +x wp6.sh_ 
 
 and then type 
 
 _sudo ./wp6.sh




