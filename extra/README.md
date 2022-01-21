## Individual Tasks

Here are a couple of relevant excercises that you can attempt. They are based on the WiFi Pineapple, Shark Jack, and the Packet Squirrel.

## WiFi Pineapple 1

Attempt setting up a different public module and see what results you get. Choose one of the following two modules.

1. The DNSspoof module, lets you redirect the user to your website of choice. Install and try redirecting the user to Facebook or any other site.

2. Another option is the Online Hash Crack module, which will submit a hash and WPA handshake to [www.onlinehashcrack.com](http://www.onlinehashcrack.com/) and attempt to brute force and crack the password.

## WiFi Pineapple 2

* Install the Evil Portal module and run the following command in a local directory: 

  ``git clone https://github.com/kbeflo/evilportals``

* Follow the instructions on the [GitHub page readme](https://github.com/kleo/evilportals), to be able to upload your landing pages to the WiFi Pineapple.

* If the uploaded page does not show up on your evil portal list, then try this command as an alternative:

  ``scp -r portal-example root@172.16.42.1:~/portals/ ``

<p align="center" width="100%">
    <img width="60%" src="https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/task_1.PNG">
</p>

* Activate and test your portals, try a few different ones from the portals folder. Go to Logs > View to see the captured credentials and information.

## Shark Jack 1

* On your shark jack device do:

  ``cd /usr/share/nmap ``
  ``mkdir scripts``

* Now on your local desktop git clone the scripts repository using the command:

  ``git clone https://github.com/vulnersCom/nmap-vulners``
  
* Use the following command to copy the folder onto your shark jack device:

  ``sudo scp -r /nmap-vulners root@172.16.24.1:/usr/share/nmap/scripts``
  
* Finally, go ahead and edit payload scan options to -p80 –-script nmap-vulners. Run the attack again and comment on your results. In case the scan took too long or failed, what type of scan do you think those commands would initiate.

## Shark Jack 2

* Utilise the push payload in the sharkjack.sh tool to quickly upload and run several different attacks using the shark jack.

* First, on your local machine git clone shark jack’s community payload repository, use the following [link](https://github.com/hak5/sharkjack-payloads).
  
* Now upload the [payload](https://github.com/hak5/sharkjack-payloads/blob/master/payloads/library/util/internet-access-tester/payload.sh) onto your shark jack. You can either use sharkjack.sh menu to upload it or the scp command.
  
* When the setup is complete, try running your shark jack in attack mode and note down the LED colour that you receive when it is plugged into your device. Now load back into Shark Jack and have a look at the payload script, evaluate what the LED colour that you received indicates.

## Packet Squirrel 1

* DNS spoof a domain name of your choice to Twitter’s IP address. You can use [who.is](https://who.is/) to find details on any domain name or IP.

* Create a custom switch folder (ending with 1/2/3) and copy another payload from the packetsquirrel-payloads folder.

  ``git clone https://github.com/hak5/packetsquirrel-payloads.git``
  
* Run the packet squirrel and document/screenshot what the script does.


