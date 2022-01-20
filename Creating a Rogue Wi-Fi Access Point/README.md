
## Setting up the lab environment with Kali Linux

* Kali is a free Debian-based Linux OS, most famous for its use in penetration testing and security auditing. Containing hundreds of useful pre-installed tools, of which some will be used throughout this workshop.

* You should have received a USB drive containing an installed copy of Kali Linux, plug it in and launch your device from USB. See [this link](https://www.acronis.com/en-gb/articles/usb-boot/) for a guide on how to launch your device from USB.  

* In the case that your system is not automatically prioritising the USB on boot up, you will have to open the BIOS or the boot manager and manually select the USB. 

* The keys to enter the boot order settings are different for every device, but the most common ones are DEL, F1, F2, F12. Eventually, if your screen looks like the screenshot below then you are ready to continue to the next step.

<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/kali-desk.jpg">
</p>

* Kali Linux should have some scripts included in the root directory; they will be useful throughout the tutorial (~/cybersecurity-resources/).

* Otherwise, open the terminal in the Kali machine and git clone the scripts into your directory using the following command. 

    ``git clone https://github.com/ysj-HIoT/cybersecurity-resources``


##  WiFi Pineapple
1. Users looking for a free network in public spaces could easily be fooled with a simple SSID, to believe that the network is managed by a legitimate organisation. 

2. Wi-Fi Pineapple is a networking device developed by Hak5, its main function is to audit and broadcast a wireless connection. However, it is also designed for scenarios where the broadcasted network acts as a honeypot for public clients. 

3. Using the Wi-Fi Pineapple, it’s possible to monitor the network connections (the device acts as a man in the middle). 

4. With Wi-Fi Pineapple hackers uses landing page to manipulate the connected users into providing their details into a fake website.

5. During this session you will practice the use of this device and learn about its security breach potential. You will also be introduced to certain methods on the internet that can further protect yourself from eavesdropping devices like this.

## setting up WiFi Pineapple

1. Connect your WiFi Pineapple nano into a USB port on your Linux system, if you are using a virtual machine, make sure that your system can see the USB connections. You can use the following command to check the USB connections.

    ``lsusb``

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_1.PNG">
</p>

2. ASIX Electronics Corp. is the device that you are looking for, if you are struggling to find it then use [this guide.](https://www.techrepublic.com/article/how-to-enable-usb-in-virtualbox/)

3. The WiFi Pineapple should have now set up an adapter on your machine as well, confirm this, open the terminal and type the following command:

    ``ifconfig``

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_2.PNG">
</p>

4. Next, disconnect the Pineapple Nano, and type the following command in the terminal:

    ``wget wifipineapple.com/wp6.sh``
  
   
5. The command should download the wp6.sh file into your current directory. This file is responsible for setting up your Wifi Pineapple. 

6. To be able to use the wp6.sh, type the folliwng command as indicated in the Figure below:

    ``chmod +x wp6.sh``
  
 and then type 
 
    ``sudo ./wp6.sh``

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_3.PNG">
</p>

7. You should now see the setup menu, run through the guided setup, answering with “Y”. 

<p align="center" width="100%">
    <img width="100%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_4.PNG">
</p>

8. Now go to the following URL http://172.16.42.1:1471, where you will be greeted with another setup page. Potentially, you might have to go into the network settings and switch to the correct network.

<p align="center" width="100%">
    <img width="30%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_5.PNG">
</p>

9. Enter your dashboard password, make sure you remember it as you will need it to access the control panel.
<p align="center" width="100%">
    <img width="80%" src="(https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_6.PNG">
</p>

10. The next stage is to set your SSID and WPA2 password. SSID is the visible name of the network, which will be broadcasted by the WiFi Pineapple. You can assign any name of your choice to your SSID. eg. NHS-Guest-WiFi, York Council Freee Wifi, etc. 

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_7.PNG">
</p>

11. Finally, set the filters to deny mode and finish the setup. Setting the filters to deny will ensure that no devices are blacklisted from this network. You should be able to login into your dashboard with the previously entered details.

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_8.PNG">
</p>

12. Finally, try connecting to the network that you set up, using a different device (phone/computer, anything with wireless connectivity). Check in the Clients tab to see if your device has made a successful connection. 

13. If you have difficulties of connecting your device you may follow the above steps or call the attention of the sessions' facilitator. 

## Connecting to the Internet

* By now you should now be able to connect to your new network, but without any internet access. That is because we have not yet set up the WiFi client mode. To do so,go to the networking settings, and locate the WiFi client tab.

* Find the SSID of a network that will connect the clients to the internet; the network can be public or private. Enter your access point’s password if you believe that its protected and click connect.

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/WiFi_Pineapple_9.PNG">
</p>

* However, be careful when choosing your interface, if you use wlan1 you might limit the capabilities of the WiFi Pineapple, disabling PineAP’s functionality. In my model below, I have connected a Wi-Fi adapter to the WiFi Pineapple, and it appears as the wlan2 interface.

<p align="center" width="100%">
    <img width="40%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Setup_Alpha_WP.PNG">
</p>

* To confirm internet connectivity, you can direct to the main dashboard page and try loading the bulletins. They will only load if you have internet access.

* Alternatively, you can now try to connect a secondary device to the Pineapple’s network and try googling something.

## Scanning Clients

* Go to the Recon page where you will find the scan option. Set it to 1 minute and run it, at this point you might be prompted with the PineAP activation, accept it. After the scan, you should have a list of connections made by the WiFi Pineapple.

<p align="center" width="100%">
    <img width="40%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/scan-settings.png">
</p>

* You can use these records to log MAC or IP addresses of the local devices. And even perform a wireless handshake capture or a deauth attack.

* Be careful as deauth will temporarily disrupt the performance of the targeted network. Since it’s a form of attack which targets the communication between the router and client, making the client think that they have been disconnected.

<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Setup_Alpha_Scan_WP2.PNG">
</p>

* To add any of the scan results to logs or filters, click the drop-down button located near the SSID’s. The pop-up window should also consist of a tab for performing deauth on the network’s clients. 

<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Setup_Alpha_Scan_WP3.PNG">
</p>

* Furthermore, using the drop-down button from the Security column, a pop-up window will appear with a functionality for capturing wireless handshakes. It is a form of authentication that the router establishes with a connecting client, the handshake can be captured and decrypted using brute force methods.

* Try capturing the wireless handshake using your WiFi Pineapple, press the Start Capture button.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/handshake-capture.png">
</p>

##  Monitoring Client Searches

* We can use the WiFi Pineapple to gather data on what the network’s users are browsing. To do so we require an additional module. Head to the modules page (/modules/ModuleManager), then go to manage modules, now click on the get modules button.

* Select and install the Dwall module.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Setup_Alpha_Scan_WP4.PNG">
</p>

* Open the Dwall module and run it, you should now be able to monitor the URLs that your network’s clients are browsing.

* Click “Enable” to start scanning. It will only show unencrypted data from HTTP, therefore most sites will not actually display in results. Try www.neverssl.com, which is an example of a website that is missing an SSL certificate. 

<p align="center" width="100%">
    <img width="100%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Setup_Alpha_Scan_WP5.PNG">
</p>

## Adding a Landing Page

* A landing page, redirecting anyone that connects to your network, is a simple method to steal the victim’s credentials. It requires you to design a website, containing a form that gets logged by the WiFi Pineapple. Captured data can be accessed by connecting via ssh.

* This method is often referred to as a honeypot, users lured in expecting a free internet connection are manipulated into forfeiting their credentials to the hacker.

* To begin the setup, head to the configuration tab on your WiFi Pineapple dashboard and scroll down to the landing page section. Activate the landing page and the auto-start settings, this will make sure that a new connection to the network will load your custom page automatically.

* The text box below is the landing page code, in the following steps you will have to enter your website into this field.

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Landing_Page.PNG">
</p>

* You can find a ready to go landing page [here](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/landing_page), clone the repository from GitHub if you haven’t yet (git clone https://github.com/ysj-HIoT/cybersecurity-resources) and go to the WiFi Pineapple folder where you should find index.php. 

* To test the PHP page, use the command php -S localhost:8000, and enter the address localhost:8000 in your browser to see your page running live.  

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Running%20php%20on%20localhost.PNG">
</p>

* If it is all working correctly then you can copy and paste the code into the landing page settings. Now with the landing page enabled and ready, try connecting a new device to the network. On successful connection, the landing page should open, enter something into the field and click reconnect.

* To view the captured data, do ssh root@172.16.42.1 (IP address of your WiFi Pineapple). The password should be identical to what you entered in setup, otherwise the default is “change_on_install”. 

When connected, type the following command 

    ``cat /tmp/wifi-passwords.txt``

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Expected%20Results.PNG">
</p>

* There is a module designed to make phishing credentials over landing pages simpler, called Evil Portal. You can search for it on the modules page or if already installed it will be at /modules/EvilPortal.



