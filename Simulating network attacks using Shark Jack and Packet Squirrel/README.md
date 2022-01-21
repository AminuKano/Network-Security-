## Shark Jack Setup

The Shark Jack is a wireless device with approximately a 15-minute battery lifetime, you can charge it with a standard USB-C charger (7 minutes to full charge).  In this section of the tutorial, we will attempt to perform a couple of network attacks/scans.

* The Shark Jack can be activated in two different modes, arming, or attack. Refer to the images below as a switch guide.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_1.PNG">
</p>

* To better understand Shark Jack’s behaviour, you can view the figure below of what the different LED colours indicate about its status.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_2.PNG">
</p>

## Shark Jack Attack

* After making sure that your device is charged, set your Shark Jack in attack mode. You should notice the LEDs blinking green until solid, the lights should then turn off and return in a magenta colour. Magenta indicates that the shark jack is ready to be plugged in and run its payload.

<p align="center" width="100%">
    <img width="40%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_3.PNG">
</p>

* The shark jack stores a script called payload, which when ran initiates a sequence of bash commands. Out of the box, it comes with the default payload which runs an nmap scan.

* Insert the shark jack it into the ethernet port on your device, shortly you should see the flickering of white lights on the shark jack; indicating the attack is processing. When finished, the LEDs will switch off, which is when you can unplug the device.

* You have successfully infiltrated the target network, running an nmap scan and potentially revealing certain vulnerabilities and open ports. To retrieve the data collected from this attack, you must launch the device in arming mode and connect to it, to view the loot.

## Arming Mode & Viewing the Loot

* Boot up the device in arming mode, with the switch in the central position. When the LED achieves a solid colour, you can go ahead and plug the Shark Jack into your computer; it will initialise itself as a network adapter. Now type ifconfig command to display the new network interface on your device. 

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_4.PNG">
</p>

* Use the following command to connect to the device:

  ``ssh root@172.16.24.1``

* Here are the default Shark Jack credentials:

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_5.PNG">
</p>

* You should have two directories, loot, and payload. In the loot directory, you can view the collected data from the past Shark Jack scans. Whereas the payload directory stores the script that runs in attack mode. 

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_6.PNG">
</p>

* To look at the script that was executed, go to the payload directory, and use cat or vim on payload.sh to view it. For tips on how to use vim, [check this out](https://www.howtoforge.com/vim-basics)

  ``vim payload.sh``
  
<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_7.PNG">
</p>

* Now we will modify the payload to scan the target subnet using nmap with options set to –sV. 

  ``NMAP_OPTIONS="-sV --host-timeout 30s --max-retries 3"``

* Now that you have modified the script, repeat the last chapter steps and launch another attack, you should expect a result with additional parameters.

## Shark Jack Firmware

* Your device is currently in factory settings, the sharkjack.sh scripts will simplify the use of your Shark Jack. [Follow this link](https://downloads.hak5.org/shark) and download the correct Sharkjack.sh for your operating system (Linux).

<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_8.PNG">
</p>

* To run the Shark Jack tool, you must make it executable using the following commands.

  ``sudo chmod +x sharkjack.sh``
  
  ``sudo ./sharkjack.sh``
  
<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_9.PNG">
</p>

* You can interact with your Shark Jack from this menu, rather than having to ssh into it every time. It must still be connected in arming mode to use this. Please ignore the Upgrade firmware option, since it often causes the Shark Jack to corrupt.

* More exercises on the Shark Jack can be found in the individual task section.

## Packet Squirrel Setup

The packet squirrel can be utilised by both system admins and penetration testers. Plugged in-between a wired connection, it provides multiple built-in functions that can be initiated by setting your Packet Squirrel in any of the 3 switch positions. Switch 1 runs a simple packet sniffing script, saving all captured packets in a .pcap file, which can be then reviewed using Wireshark. If activated in the switch 2 position, the device will spoof the DNS, interrupting the connection between a specific domain and possibly redirecting to another page. The final switch 3 sets up a VPN tunnel into the network, allowing remote connectivity from outside of the network via ssh.

The packet squirrel requires a minimum setup, it is a plug-in-play device. Your Packet Squirrel will substitute an ethernet connected device on the network; you will then use another ethernet cable to connect the other side of your Packet Squirrel to the original device on the network. To power it, you will need a USB micro b charger, and finally for storage, use an NTFS formatted USB stick.

<p align="center" width="100%">
    <img width="100%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_1.PNG">
</p>

## Packet Sniffer Switch

* This method can be run without having to set up anything in arming mode. Set the switch to the left position and power up your Packet Squirrel. It should flash green while booting up, and finally orange indicating that the packet sniffer is running.

* Allow it to run for a while (1-2 minutes), then unplug it from power. Connect the USB stick to your device to view the loot; if your Linux has any problems mounting the USB stick, then make sure that your [ntfs-3g module](https://installlion.com/kali/kali/main/n/ntfs-3g/install/index.html) is updated. Or if you are running a virtual box and having USB problems then you can also refer to [this](https://www.techrepublic.com/article/how-to-enable-usb-in-virtualbox/) for help.

    ``Sudo apt-get install ntfs-3g``

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_2.PNG">
</p>

* Launch Wireshark and open the .pcap file. You should now be able to see all the packets that have been captured by the Packet Squirrel.

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_3.PNG">
</p>

* While running your Packet Squirrel in switch 1 position, connect to a HTTP website, then attempt to find the packets that show this connection, using Wireshark.

* To filter HTTP traffic you can use the following commands in the “Apply a display filter” field.

    ``tcp port 80 or tcp.port == 80``
 
## DNS Spoof Switch

* The second switch performs a DNS spoof on the connected device/network. Using this function, the packet squirrel can redirect connection attempts to different domains. 

* You must configure first for this method to work, otherwise, all domains will be spoofed on launch making no site accessible. Put your Packet Squirrel’s switch in the most-right position to launch it in arming mode. When loading it should flash a blue light.

* Use the following command to connect to the Packet Squirrel:

    ``ssh root@172.16.32.1``
    
* The default password is hak5squirrel

* In case of any problems, make sure all cables are properly plugged into your packet squirrel, the ifconfig command should display an IP like 172.16.32.1.

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_4.PNG">
</p>

* Now that you are connected, go to the switch 2 folder; the directory should be at ~/payloads/switch2.

    ``cd ~/payloads/switch2``
    
* The Packet Squirrel has a more updated text editor compared to some of the other Hak5 devices, use the following command to open the configuration file.

    ``nano spoofhost``
    
* You should see a single variable called address, the first section (www.facebook.com in the figure below) is where you enter the domain name that you would like to spoof. The second section is the IP address that the user will be redirected to.

<p align="center" width="100%">
    <img width="40%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_5.PNG">
</p>

* After editing the file, run the Packet Squirrel in the switch 2 position, to test the DNS spoofing payload. You should be able to browse the internet but searching for your spoofed domain would return either a redirection to 74.125.142.147 (google.com) or a security error by the browser.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_6.PNG">
</p>

* You can confirm the successful spoofing using the following command:

    ``ping``
    
<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_7.PNG">
</p>

* Notice how the first ping shows Facebook to be at address 74.125.142.147 and the second ping shows 157.240.31.35. This confirms a successful DNS spoof.

## VPN Tunnel Switch

* The third payload creates a VPN tunnel from the packet squirrel, encrypting the device's connection to the internet. A VPN is also commonly used to bypass content restrictions in certain countries, but with a certain setup, it is possible to remotely connect back to the packet squirrel via the VPN server (from anywhere on the internet).

* Launch the packet squirrel in configuration mode and ssh to it and go to the switch 3 payload. 

    ``ssh root@172.16.32.1``
    ``cd switch3``
    ``nano payload.sh``
    
<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_8.PNG">
</p>

* Edit the line containing FOR_CLIENTS, so that it looks like the this:

    ``FOR_CLIENTS=1``
    
* Now all there is left to do is to reset the packet squirrel into the 3rd switch position, and you will be connected to the default-free VPN server.

<p align="center" width="100%">
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_9.PNG">
</p>

## Packet Squirrel Custom Payloads

The packet squirrel automatically prioritises payloads set up on the USB drive. During this section, you will learn how to configure and launch an nmap scan using the Packet Squirrel. 

* To run custom payloads on the Packet Squirrel we will need to create new directories on the USB, a folder called "payloads" containing switch1, switch2, or switch3 folders; depending on the position that you would like your script to run on.

* Use the following command to create a new directory:

    ``mkdir switch2``

<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_10.PNG">
</p>

* Git clone the Hak5 Packet Squirrel community repository to obtain several different pre-written payloads.

    ``git clone https://github.com/hak5/packetsquirrel-payloads.git``
    
* From your new folder of payloads go to packetsquirrel-payloads/payloads/library/recon/nmapdump and copy the payload.sh file on to the USB.

* Now run the Packet Squirrel in its respectable switch position to the new payload folder; in the example the Packet Squirrel is run on switch 2. Report on the loot that you have found in /media/kali/USB/loot/nmapdump/.

<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/squirrel_11.PNG">
</p>
