
## Setting up the lab environment with Kali Linux

* Kali is a free Debian-based Linux OS, most famous for its use in penetration testing and security auditing. Containing hundreds of useful pre-installed tools, of which some will be used throughout this workshop.

* You should have received a USB drive containing an installed copy of Kali Linux, plug it in and launch your device from USB. See [this link](https://www.acronis.com/en-gb/articles/usb-boot/) for a guide on how to launch your device from USB.  

* In the case that your system is not automatically prioritising the USB on boot up, you will have to open the BIOS or the boot manager and manually select the USB. 

* The keys to enter the boot order settings are different for every device, but the most common ones are DEL, F1, F2, F12. Eventually, if your screen looks like the screenshot below then you are ready to continue to the next step.

* Kali Linux should have some scripts included in the root directory; they will be useful throughout the tutorial (~/cybersecurity-resources/).

* Otherwise, open the terminal in the Kali machine and git clone the scripts into your directory using the following command. 

" git clone https://github.com/ysj-HIoT/cybersecurity-resources "

##  WiFi Pineapple
* 1. Users looking for a free network in public spaces could easily be fooled with a simple SSID, to believe that the network is managed by a legitimate organisation. 

* 2. Wi-Fi Pineapple is a networking device developed by Hak5, its main function is to audit and broadcast a wireless connection. However, it is also designed for scenarios where the broadcasted network acts as a honeypot for public clients. 

* 3. Using the Wi-Fi Pineapple, it’s possible to monitor the network connections (the device acts as a man in the middle). 

* 4. With Wi-Fi Pineapple hackers uses landing page to manipulate the connected users into providing their details into a fake website.

* 5. During this session you will practice the use of this device and learn about its security breach potential. You will also be introduced to certain methods on the internet that can further protect yourself from eavesdropping devices like this.

## setting up WiFi Pineapple

* 1. Connect your WiFi Pineapple nano into a USB port on your Linux system, if you are using a virtual machine, make sure that your system can see the USB connections. Use lsusb to check this

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_1.PNG)

* 2. ASIX Electronics Corp. is the device that you are looking for, if you are struggling to find it you use [this guide.](https://www.techrepublic.com/article/how-to-enable-usb-in-virtualbox/)

* 3. The WiFi Pineapple should have now set up an adapter on your machine as well, confirm this, open the terminal and type the following command:

 "ifconfig"


![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_2.PNG)

* 4. Next, disconnect the Pineapple Nano, then type the following command in the terminal

   _wget wifipineapple.com/wp6.sh_ 
   
* 5. The command should download the wp6.sh file into your current directory. This file is responsible for setting up your Wifi Pineapple. 

* 6. To be able to use the wp6.sh, type the folliwng command as indicated in the Figure below:

 _chmod +x wp6.sh_ 
 
 and then type 
 
 _sudo ./wp6.sh

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_3.PNG)

* 7. You should now see the setup menu, run through the guided setup, answering with “Y”. 

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_4.PNG) 


* 8. Now go to the following URL http://172.16.42.1:1471, where you will be greeted with another setup page. Potentially, you might have to go into the network settings and switch to the correct network.

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_5.PNG)#

* 9. Enter your dashboard password, make sure you remember it as you will need it to access the control panel.

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_6.PNG)

* 10. The next stage is to set your SSID and WPA2 password. SSID is the visible name of the network, which will be broadcasted by the WiFi Pineapple. You can assign any name of your choice to your SSID. eg. NHS-Guest-WiFi, York Council Freee Wifi, etc. 

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_7.PNG)

* 11. Finally, set the filters to deny mode and finish the setup. Setting the filters to deny will ensure that no devices are blacklisted from this network. You should be able to login into your dashboard with the previously entered details.

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_8.PNG)

* 12. Finally, try connecting to the network that you set up, using a different device (phone/computer, anything with wireless connectivity). Check in the Clients tab to see if your device has made a successful connection. 

* 13. If you have difficulties of connecting your device you may follow the above steps or call the attention of the sessions' facilitator. 

## Connecting to the Internet

* By now you should now be able to connect to your new network, but without any internet access. That is because we have not yet set up the WiFi client mode. To do so,go to the networking settings, and locate the WiFi client tab.

* Find the SSID of a network that will connect the clients to the internet; the network can be public or private. Enter your access point’s password if you believe that its protected and click connect.

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_9.PNG)

* However, be careful when choosing your interface, if you use wlan1 you might limit the capabilities of the WiFi Pineapple, disabling PineAP’s functionality. In my model below, I have connected a Wi-Fi adapter to the WiFi Pineapple, and it appears as the wlan2 interface.


