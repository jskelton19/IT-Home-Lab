6/6/26

Forgot Admin Account Password, Must Reset



First I changed the settings on the VM, on the storage tab I made sure I selected the Iso to run on the CVD.



On the motherboard Tab I changed the boot to be Optical Drive, then storage, then floppy disk. 



Once I started the VM I spammed F12 then clicked esc and it took me to windows installation scree. Ran Shift + F10 to open CMD



**In command I ran** 

\-diskpart

**list volume** 

to list all the volume drives on the PC to see which drive has the windows partition.

&#x20;

**I had both a C: and A D:. Could not tell which one had the windows files on so.**

\- I ran C: to open the C drive and then ran -dir to see whats in that directory. There was nothing

\- I ran D: and ran -dir and seen the windows files. Like program files, users etc. 



**to replace the accessibility with a cmd promot I ran** 

\-  move D:\\Windows\\System32\\Utilman.exe D:\\Windows\\System32\\Utilman.exe.bak

\-  copy D:\\Windows\\System32\\cmd.exe D:\\Windows\\System32\\Utilman.exe



**To Rest the password**

\- net user Administrator Lab123!( to change the password)



\- the end.



