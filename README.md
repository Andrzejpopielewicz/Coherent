# Coherent
Free software for coherent OS. 

You Will find here the virtual machine image usable 
in latest editions of Virtualbox in Win10. 

Copy the file coherent3.zip into VirtualBox VMs directory and uncompress. It will create coherent3 virtual machine in Your VirtualBox.

It is ready to be started, no configuration needed. The virtual disk of this machine can be used in other systems like MacOS or Linux ,

but we do NOT tested yet. The virtual disk was tested OK in WinXP.

In general virtual machine should be defined as follows:

1)one processor

2)1000 MB ram

3)64/128 MB video memory

4)ide piix4 controller

5)chipset piix3, ps2 mouse

6)ioapic enabled

7)networking : NAT, 82543gc card
 
Starting:

1) after boot choose 0 partition

2) enter cohtestSAY13z as kernel name  

3) wait till login prompt

4) user root, password : coherent

Using:

After login enter :

  ./prepare

If you want to use network enter : 

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
  
do not logoff and switch back to first virtual console
 
  ALT/F1
  
You can now use networking. 
To see want to see Your gmail mails , configure mutt and enter

  mutt -f imaps://imap.gmail.com/INBOX

Other useful commands 

  ifconfig ipro100

This Will show the network parameters. 

You can check arp status with :

  arp ipro100

Other useful commands

  lynx http://www.xfree86.org 

  lynx news:comp.os.coherent 
  or more safe :
  lynx news://news.icm.edu.pl/comp.os.coherent

  gopher gopher.floodgap.com 

  mutt -f imaps://imap.gmail.com/Inbox 

  dig8 www.mutt.org 

  gethost www.oracle.com 

  ping www.gnu.org 

  telnet pub400.com 

  lynx http://ftp.xfree86.org/public 

  lynx https://www.google.pl
  
  lynx gopher://gopher.floodgap.com
  
  lynx http://server505065.nazwa.pl

  lynx telnet://telehack.com
  
  ntpdate pool.ntp.org

  netstat
  
We suggest to do the following. First check if sizes of cohtestSAY13z , autoboot and coherent are equal. If not , then do

   cp cohtestSAY13z coherent ;
   cp cohtestSAY13z autoboot ;
   
It will may Your life easier :).
  
Only one instance of ping command can be used at a given time.

Before using ntpdate remowe pool.ntp.org entry from /etc/hosts if present.

IP addresses of the hosts may change in time, so if suddenly the connection does not work remove the corresponding entry in /etc/hosts.

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

  I210
 


Important : Of course before using mutt You have to configure
.muttrc file, it is enough to insert Your gmail paswords and user if You have gmail account. More precisely, usual gmail account password will NOT work.
Simply after logon in gmail account create so called application specific password and use this password in mutt. The name of the application in gmail is not important, You can for example name it mutt.

Warning : do NOT use ahci at driver, use nonahci at driver, which is installed by default. Otherwise You risk to corrupt Your virtual disk.

Remark : we suggest to change the PATH to :
  
  export PATH=$PATH:/usr/local/X11R6/bin
  
After this both X window managers namely mwm2 and icewm will work fine. If You do not do it icewm will work but will be not usable :). And icewm is obviously better. Also notice , that xclock MUST be started just after start of the X , for example using xclock icon on the taskbar (in the case of icewm) or xclock command in the menubar(in the case of mwm2).
IMPORTANT:
Kernels cohtestSAY13z, cohtestSAY39z and cohtestSAY44z were developed and tested using SATA controllers working in IDE legacy mode. Sometimes BIOS allows for setting SATA0 mode, it corresponds to IDE legacy mode.
If SATA0 is disabled then IDE native mode is active, it is NOT supported yet. AHCI mode is supported but does NOT work correctly yet. Only kernels cohtestSAY13z and cohtestSAY39z work fine in VB.
In both cases PIIX3 chipset and PIIX4 IDE controller must be used in VB. Kernel cohtestSAY44z will work in VB if ICH6 IDE controller and ICH9 chipset are set, but in this case networking will NOT work.
If used in standalone system the kernel cohtestSAY44z offers very fast download speed in lynx , circa 5-10 times faster than in case of cohtestSAY39z or cohtestSAY13z. Notice that if kernel cohtestSAY39z is used,
DVD burner must be attached to SATA port 1  in standalone system, it corresponds to secondary master. Supplied VB configuration uses this setting.
   

