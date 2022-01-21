## Shark Jack Setup

* The Shark Jack is a wireless device with approximately a 15-minute battery lifetime, you can charge it with a standard USB-C charger (7 minutes to full charge).  In this section of the tutorial, we will attempt to perform a couple of network attacks/scans.

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
    <img width="80%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_8.PNG">
</p>

* To run the Shark Jack tool, you must make it executable using the following commands.

  ``sudo chmod +x sharkjack.sh``
  
  ``sudo ./sharkjack.sh``
  
<p align="center" width="100%">
    <img width="70%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/sharkjack_9.PNG">
</p>

* You can interact with your Shark Jack from this menu, rather than having to ssh into it every time. It must still be connected in arming mode to use this. Please ignore the Upgrade firmware option, since it often causes the Shark Jack to corrupt.

* More exercises on the Shark Jack can be found in the individual task section.











