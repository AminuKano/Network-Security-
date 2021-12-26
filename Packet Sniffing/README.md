# Packet sniffing (Time: 30 Minutes)

* Packet sniffing is the practice of gathering, collecting, and logging some or all packets that pass through a computer network, and it's a common practice by:

  - Network engineers to monitor network traffic and understand valuable network infrastructure and performance insights.
  - Hackers to launch network attacks - Sniffing attacks: eavesdrop on a physical network (wired or wireless).
  
* A packet sniffer itself is passive. It observes messages being sent and received by applications and protocols running on your computer, but never sends packets itself. 

* There are different packet sniffers, including Wireshark, Netwox, Scapy, etc. In this session you’ll get acquainted with Wireshark (packet sniffer), and make some simple packet captures and observations. 

Figure 1 below shows the structure of a packet sniffer. 

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Packet_Snippe_structure.PNG)

## Running Wireshark

*	Start Wireshark by clicking the Wireshark icon. 

*	When you run the Wireshark program, you’ll get a startup screen. To begin packet capture, select the Capture pull down menu and select Interfaces. This will cause the “Wireshark: Capture Interfaces” window to be displayed, as shown in Figure below:

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Initial_Wireshark_screen.PNG)

* Choose the interface on which your computer is connected to: WiFi, or Ethernet. You may ask the instructor if you are struggling to understand which interface to choose.

* Once you begin packet capture, a window similar to that shown in Figure 3 will appear.  This window shows the packets being captured.  

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Wireshark_screen.PNG)

* By selecting Capture pulldown menu and selecting Stop, you can stop packet capture. But don’t stop packet capture yet.  Let’s capture some interesting packets first.  

* To do so, we’ll need to generate some network traffic.  Let’s do so using a web browser, which will use the HTTP protocol that we will study in detail in class to download content from a website.

* Start up your favorite web browser, which will display your selected homepage.

* While Wireshark is running, enter the URL in your browser: http://gaia.cs.umass.edu/wireshark-labs/INTRO-wireshark-file1.html and have that page displayed in your browser

* After your browser has displayed the INTRO-wireshark-file1.html page (it is a simple one line of congratulations), stop Wireshark packet capture by selecting stop in the Wireshark capture window. 

* Type in “http” (without the quotes, and in lower case – all protocol names are in lower case in Wireshark) into the display filter specification window at the top of the main Wireshark window.  Then select Apply (to the right of where you entered “http”).

* Find the HTTP GET message that was sent from your computer to the gaia.cs.umass.edu HTTP server. (Look for an HTTP GET message in the “listing of captured packets” portion of the Wireshark window (see Figure 3) that shows “GET” followed by the gaia.cs.umass.edu URL that you entered. 

![](https://github.com/CS-Outreach-Session/Network-Security-/blob/main/images/Wireshark_Captured_screen.PNG)

## HTTP Authentication

* Start up the Wireshark packet sniffer
* Enter the following URL into your browser http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html
* Type the requested user name and password into the pop up box.
	- Username is “wireshark-students” – without the quotes
  - password is “network” – without the quotes
* Stop Wireshark packet capture and enter “http” in the display-filter-specification window, so that only captured HTTP messages will be displayed later in the packet-listing window.  

* The username (wireshark-students) and password (network) that you entered are encoded in the string of characters (d2lyZXNoYXJrLXN0dWRlbnRzOm5ldHdvcms=) following the “Authorization: Basic” header in the client’s HTTP GET message.  While it may appear that your username and password are encrypted, they are simply encoded in a format known as Base64 format. The username and password are not encrypted! 

* To see this, go to  http://www.motobit.com/util/base64-decoder-encoder.asp and enter the base64-encoded string d2lyZXNoYXJrLXN0dWRlbnRz and decode.  Voila!  You have translated from Base64 encoding to ASCII encoding, and thus should see your username!  

* To view the password, enter the remainder of the string Om5ldHdvcms= and press decode.  Since anyone can download a tool like Wireshark and sniff packets (not just their own) passing by their network adaptor, and anyone can translate from Base64 to ASCII (you just did it!), it should be clear to you that simple passwords on WWW sites are not secure unless additional measures are taken. 

Congratulations you have finished this session!

## Refferences 
Kurose, J. and Ross, K., 2010. Computer networks: A top down approach featuring the internet. Peorsoim Addison Wesley.
