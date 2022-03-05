# Coherent
Free software for coherent OS
You Will find here the virtual machine image usable 
In latest editions of Virtualbox for XP and 
WIN10. 

The virtual machine should be defined as follows:
1)one processor
2)700 MB ram
3)64 MB video memory
4)ide piix4 controller
5)chipset piix3, ps2 mouse
6)ioapic enabled
7)networking : NAT, 82543gc card
 
Starting:
1) after boot choose 0 partition
2) enter cohtestSAY12z as kernel name
3) wait till login prompt
4) user root, password : coherent

Using:
After login enter :

  bash

If you want to use Network enter : 

  dhcpclient

Then : 

  ifconfig ipro100

This Will show the network parameters. 
You can check arp status with :

  arp ipro100

Other useful commands

  lynx http://www.xfree86.org 

  lynx news:comp.os.coherent 

  gopher gopher.floodgap.com 

  mutt -f imaps://imap.gmail.com/Inbox 

  dig8 www.mutt.org 

  gethost www.oracle.com 
  ping www.gnu.org 

  telnet pub400.com 

  lynx http://ftp.mutt.org 

  lynx https://www.google.pl 

Xfree86 VESA server is AVAILABLE. 

Useful system commands

  scanpci -v 

  mptable  

  ndf 
  

Supported Network cards :

  82543gc (virtual box) 

  82541pi 

  82574L 

  82576NS (one port only) 
 


Of course before using mutt You Have to configure
.muttrc file. 

