# Coherent
Free software for coherent OS. 

You Will find here the virtual machine image usable 
In latest editions of Virtualbox for XP and 
WIN10.

Copy the file coherent3.zip into VirtualBox VMs directory and uncompress. It will create coherent3 virtual machine in Your VirtualBox.

It is ready to be started, no configuration needed. The virtual disk of this machine can be used in other systems like MacOS or Linux,

but we do NOT tested yet.

In general virtual machine should be defined as follows:

1)one processor

2)700 MB ram

3)64 MB video memory

4)ide piix4 controller

5)chipset piix3, ps2 mouse

6)ioapic enabled

7)networking : NAT, 82543gc card
 
Starting:

1) after boot choose 0 partition

2) enter cohtestSAY13z as kernel name, or wait for autoboot

3) wait till login prompt

4) user root, password : coherent

Using:

After login enter :

  ./prepare

If you want to use Network enter : 

  dhcpclient
  
Wait for the reasonable output
Then check if networking works

  ping www.ibm.com
  
If ping works enter ctrl/c to stop it.
Then enter

  ALT/F2
  
to change the virtual console , login to Coherent
Then enter

  /usr/bin/ticker &
  
and switch back to first virtual console
 
  ALT/F1
  
You can now use networking. 
To see Your gmail mails enter

  mutt -f imaps://imap.gmail.com/INBOX

Other useful commands 

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

  lynx http://ftp.xfree86.org/public 

  lynx https://www.google.pl
  
  lynx gopher://gopher.floodgap.com
  
  ntpdate pool.ntp.org
  
Only one instance of ping command can be used at a given time.

Before using ntpdate remowe pool.ntp.org entry from /etc/hosts if present.

Xfree86 VESA server is AVAILABLE. 

Useful system commands

  scanpci -v 

  mptable  

  ndf 
  
  mc -c
  

Supported Network cards :

  82543gc (virtual box) 

  82541pi 

  82574L 

  82576NS (one port only) 
 


Important : Of course before using mutt You Have to configure
.muttrc file, it is enough to insert Your gmail paswords and user if You have gmail account. 

