# Network Firewall and Malicious software

Dr Aminu Usman
## About Firewalls

* A  Firewall is part of computer system or network designed to stop unauthorized traffic flowing from one network to another. 
* A  Firewall Separate trusted and untrusted components of a network.
* A  Firewall Differentiate networks within a trusted network.
Main functionalities of a Firewall are filtering data, redirecting traffic and protecting against network attacks as illustrated in the Figure below.

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_illustration.PNG)

## Viruses and Other Malware
* A virus or malicious code program is written for a variety of non-criminal purposes including advertisements, jokes, and political messages. But it can be a threat to your devices, online privacy and your cybersecurity. 
* It’s software that cyber attackers develop to gain access or cause damage to a computer or network, usually without the victim’s knowledge. 
* Example of malicious software include: Viruses, Malware, Spyware, Adware, Rootkits, Ransomware, Worms, and Keyloggers.
### Viruses
* Viruses operate in four primary environments: file viruses, boot viruses, macro viruses, and network viruses. 
   1. File viruses infect their targets in several ways: as a parasite, as a companion, or through file system specific features known as link viruses. 
   2. Boot viruses attack either the boot sector of the system, the master boot record, or change the system pointer to an active boot sector. 
   3. Macro viruses are most commonly associated with common business software and infect documents, spreadsheets, databases, and presentation files. 
   4. Network viruses attack the networks themselves or e-mail systems of the networks in order to spread themselves. 
### Worms
  * A computer worm is also a piece of software that copies itself elsewhere. However, unlike a virus, it does not attach itself to, or modify, other files. The worm is a stand-alone piece of code, although it may need to use another program to spread, it does not change that program in any way.
  1. The worm may damage and compromise the security of the computer.
  2. First known Internet worm was the [Morris worm](https://en.wikipedia.org/wiki/Morris_worm).

### Trojan Horses
  * A Trojan horse is commonly an unauthorized program contained within a legitimate program that performs functions unknown (and probably unwanted) by the user. Trojan horses typically masquerade as something desirable, a joke program, a legitimate software program, or some other type of executable file that the user wishes to install and run. 
 
  * There are numerous types of Trojans including: Remote Access Trojans, Password Sending Trojans, Keyloggers, Destructive, Denial of Service Attack Trojans, Proxy/Wingate Trojans and Software Detection Killers

### Adware and Spyware
  * Adware and spyware are types of programs that could be contained in e-mail attachments, downloaded as part of another software program, or downloaded from a website. 
     - Adware is a type of program that is, essentially, a pain to user that manifests itself in several ways including changes to the browser, redirecting startup pages on the Internet browser, replacing the search function within the browser, and generating pop-up ads and frames that can be difficult to delete or shut down. 
     - Spyware programs are applications that send information via the Internet to the publishers or programmers for marketing purposes without obvious notification to users. Spyware can send a variety of information about the user's computer hardware, software, browsing habits, and other personal information to the host marketer or programmer. 


## Network Firewall Virtualisation Exercise

* Start the Firewall program by downloading the visual tool from [this link](https://kevincurran.org/com320/labs/Firewall/FirewallVisualizationTool.jar). Click on the download button. After successfully downloading the file, double-click on the file to start the program. The file is a .jar file; it requires Java installed on your PC to run the program successfully. If you do not have java installed on your machine, you may use [this link](https://www.java.com/en/download/help/windows_manual_download.html#download) to download and install the application on your PC.

* By double-clicking the file, you should see a screen similar to the one below:

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_P1.PNG)

* Choose “no firewall” and click next.  The following screen will appear:

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Firewall_P2.PNG)

* Click the paly button.  Note that the traffic flows both from the “cloud” or internet to the client machines.  
* By default, there is no malicious traffic flowing to the machines.  Click on the OS Exploit option.  Eventually, you’ll see a similar red colored bug flow from the internet into the local area network and land on a machine, infecting the machine.  Once a machine is infected, it is marked as such with the “international No” emblem. Let’s see how configuring a firewall will help prevent such infections.  

## FIREWALL Simulations 
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
