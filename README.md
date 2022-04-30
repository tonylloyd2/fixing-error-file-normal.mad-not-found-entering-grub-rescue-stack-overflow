# fixing-error-file-normal.mad-not-found-entering-grub-rescue-stack-overflow
works follow the steps and patitience contact  lloydkatila@gmail.com for more info


STEP 1 : **try to get into grub**
do this
uset `set` to locate where grub is installed in your case it would be msdos1 partition

STEP 2 :**set root and prefix**
    
  

    set root=(hd0,msdos1)

then type:

set prefix=(hd0,msdos1)/usr/lib/grub

STEP 3 :**TRY  insmod**

    insmod normal
this should not give out an error .If so reset the root partition or use the ls to find the ext4* partition

STEP 4:**ENTER GRUB**
type the normal command to enter grub

    normal

*DONT FORGET YOUR EXT4 PARTITION*

STEP 5 : **Find the ;lost and found files**

    ls (hd0,msdos1)
atleast your output should begin with "lost+found" and contain /boot/ and /etc/

STEP 6: **List the vm and intrd**

    ls -l (hd0,msdos1)/boot

note the vmlinuz
in my case it was "vmlinuz-5.15.0-kali.0amd......."not really sure 

**NOTE   FOR GPT USERS vmlinz might contain generic** 


PICK THE LAST vmlinuz in the list if you have multiple

ALSO NOTE "initrd.img....." code name**

STEP 7 : **SET ROOT **

    set root=(hd0,msdos1)

STEP 8 : **SET vmlinuz and intrd**

    linux /boot/**enter here your vmlinuz name code then one space**  root=/dev/sda1        

#**for hd1 users use sdb
 hd2 users use sdc
 hd3 users use sdc
**

 next set the initrd

    initrd /boot/**initrd.....ENTER YOUR INITRD CODE NAME
**
if you recorded no errors  then you are almost done easy right!!!

    boot

system should boot successfully

FINAL: **UPDATE & INSTALL GRUB**
press 

> ctr +alt + t
to the terminal enter :

    sudo update-grub2

> install grub

    sudo grub-install /dev/sda1

wallah
reboot and see the magic

find the whole tutorial in my git account link


https://github.com/katilalloyd/fixing-error-file-normal.mad-not-found-entering-grub-rescue-stack-overflow



