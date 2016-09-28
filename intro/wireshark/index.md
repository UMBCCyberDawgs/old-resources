---
title: Wireshark
authors:
  - Jorge Teixeira
---

## About Wireshark 

Wireshark (https://www.wireshark.org/) is a popular network protocol analyzer.
It lets you decode most network protocols and collect statistics on network
traffic. 

Wireshark can also be used to capture traffic in real-time, via libpcap/WinPcap
(a user-mode packet capture library implementing the pcap API). 

While Wireshark uses a Qt-based GUI, similar text-mode applications can be
found in tshark and tcpdump. Internally, Wireshark relies on Berkeley Packet
Filter (BPF) rules to filter captured traffic. A comprehensive list of
supported fields can be obtained from within Wireshark itself, and custom
dissectors can be added via Lua plugins.

## Getting Wireshark 

The latest stable version of Wireshark is available at their
[website](https://www.wireshark.org/download.html) or from your OS package
manager (e.g.: apt-get install wireshark, dnf install wireshark). 

## Installing Wireshark 

On Windows, just follow the prompts accepting the defaults. Make sure you
install WinPcap, if you haven't done so already. Reboot if prompted to do so. 

On Debian-based systems you may be prompted whether to allow non-root users to
capture traffic. If you do not, you will need to start Wireshark with elevated
privileges.

## Starting Wireshark 

On Windows you should be able to simply start the program normally. If no
interfaces are available and you are sure that WinPcap is properly installed,
try running Wireshark as an Administrator. 

On Debian-based systems you can add yourself to the group wireshark to be able
to capture live traffic, provided you allowed that during install. Otherwise
try running Wireshark as root. 

## Capturing live traffic 

To capture live traffic, click the icon on top left that looks like a gear
inside a circle (Capture options), select the interface you want, and then
click Start. To stop, click the red square icon (Stop capturing packets) on
top left.

## Loading an existing capture file 

On the menu bar, click File -> Open, and navigate to the file that you want to
load.

## Filtering traffic 

On the display filter bar, type the BPF expression that you want to use. Valid
expressions will turn the bar green. You can see a searchable tree of available
dissectors by clicking on Expression... to the right of the bar.

Example filters: 

* `udp`
* `http and !(ip.addr == 24.6.125.19)`
* `(frame.cap_len < 100) and !arp and !dns`
* `tcp.dstport == 443`
* `tcp.stream eq 336`

## Searching 

On the menu bar, click Edit -> Find Packet..., and select String on the
rightmost dropdown box, before the find bar. Then select Packet bytes on the
leftmost dropdown box. You can now enter a string to search for in the find
bar.

## Extracting files 

If you detect a bytestream of a file, you can extract it by selecting it,
right-clicking it with the mouse, choosing Export Packet Bytes... and saving it
to a file.

Example: 

* Download exercise1.pcapng and open it with Wireshark.
* Use filter `frame.number == 119`
* Select Line-based text data: text/html in the packet dissectors area
* Right-click with the mouse, select Export Packet Bytes..., and save the file.
* You should now be able to open the file with a browser or text editor.

