Facilitator 
Dr Aminu Usman
## About Firewalls

* A  Firewall is part of computer system or network designed to stop unauthorized traffic flowing from one network to another. 
* A  Firewall Separate trusted and untrusted components of a network.
* A  Firewall Differentiate networks within a trusted network.
Main functionalities of a Firewall are filtering data, redirecting traffic and protecting against network attacks.

## Introduction to Malicious software
* Malicious software can be a threat to your devices, online privacy and your cybersecurity. 
* It’s software that cyber attackers develop to gain access or cause damage to a computer or network, usually without the victim’s knowledge. 
* Example of malicious software include: Malware, Spyware, Adware, Rootkits, Ransomware, Worms, and Keyloggers.
* Among different forms of malicious software, Malware or Malware is often difficult to detect, and network are typically infected without the user even noticing, it can be one of the primary threats to your network, personal information or network inprastructurer.

## Network Firewall Virtualisation Exercise

* Start the Firewall program by downloading the visual tool from [this link](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/Tools/FirewallVisualizationTool.jar). Click on the download button. After successfully downloading the file, double-click on the file to start the program. The file is a .jar file; it requires Java installed on your PC to run the program successfully. If you do not have java installed on your machine, you may use [this link](https://www.java.com/en/download/help/windows_manual_download.html#download) to download and install the application on your PC.

* By double-clicking the file, you should see a screen similar to the one below:

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_P1.PNG)

* Choose “no firewall” and click next.  The following screen will appear:

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_P2.PNG)

* Click the paly button.  Note that the traffic flows both from the “cloud” or internet to the client machines.  
* By default, there is no malicious traffic flowing to the machines.  Click on the OS Exploit option.  Eventually, you’ll see a similar red colored bug flow from the internet into the local area network and land on a machine, infecting the machine.  Once a machine is infected, it is marked as such with the “international No” emblem. Let’s see how configuring a firewall will help prevent such infections.  

## FIREWALL Configuration
* Start a new session by clicking File -> New in the upper window of the tool.  This time, choose the Parameter firewall.  The window that comes up will look like this:

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_P3.PNG)

* You now have a firewall between the internet (represented by a cloud) and your network router.  Click the play button and watch what happens.  Do you see traffic flowing from the internet into your system or from your network to the internet?  why or why not?

* Add some active attacks by clicking on several different options.  Are these attacks able to get to your network?  Do you feel your system is secure?  What’s wrong with this scenario?

* Configure your firewall to allow traffic to flow in and out of your network.  Do this by choosing the ‘options’ tab at the top of the tool and define firewall rules.  You should see a screen similar to the one below: 

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_P4.PNG)

* Name your firewall rule (typically with a name that focuses on a given subject or attack).  The “Source IP” option and port refer to how you want the firewall to recognize a given source IP/Port combination and respond.  The Destination is similar but focusing on a destination rule.  

* The goal of any good firewall configuration is to identify legitimate traffic while restricting malicious traffic.   Try setting the following firewall rule:
	- Rule Name:  DNS Rule
	- Source IP:  DNS,  Source Port: 53
	- Destination IP:  Any,  Destination port *
	- Protocol:  Any.  

* Click “Save Rule”.  You should now see the rule in your Active Rules box.  Click “close” and you should be back to your Network Firewall Visualization Tool window.  Click the play button and watch what happens.  

* You may need to move the speed bar to the right for a higher speed of traffic.

* What traffic now flows through the firewall?  Add some active attacks and watch if they flow through the firewall.

* Would you claim your rule is now sufficient to allow traffic to flow for a typical network?  Why or why not? Do any of the active attacks now work against machines behind the firewall?

# References

Warner, J., Musielewicz, D., Masters, G.P., Verett, T., Winchester, R. and Fulton, S., 2010. Network firewall visualization in the classroom. Journal of Computing Sciences in Colleges, 26(2), pp.88-96.
