

# network-config-raspbianOS-12
How you do networkchanges on sdcard and use it with cable on raspbian12

This is for those that thiers raspberry pi has dropped connection with wifi and you can not connect to it with ethernet cable or wifi. 

You need:
1 Sdcard reader 
2 a computer that can read linux filesystem
3 a ethernet cable. 

Following scenario:
One day you notice that your Rpi has
dropped connection with your wifi and you 
can not connect to it again not even with ethernet cable, nor if you pull the power and reboot. 

Here is a trick, note this trick works only for raspbian os12 and above. 

1 Pull out sdcard from rpi put it in your sdcard adapter and put in your sdcard reader connected to your computer. 

2 In your file explorer of choice you should now see your sdcard, expand the view and you should now see bootfs an rootfs 

3. Open your Terminal window of choice and cd into your sdcard cd / ENTER

4. / cd media/<your-user>/rootfs

5. your are now inside your sdcard type ls ENTER.

6. you should now see a bunch of files and directorys.

7. we will now find a file called interfaces thats inside a directory called /network that has it place inside a directory called /etc.

8. so punch in cd /etc/network ENTER

9. punch in ls -a

10. you should now see a couple of files and directorys.

11. punch in sudo nano interfaces

12. nano opens the file interfaces and it can be empty or filled with network stuff

13. Here you can do two things try to edit
the information so it fits your network or erase all info below

```
# interfaces(5) file used by ifup(8) and ifdown(8)
# Include files from /etc/network/interfaces.d:
source /etc/network/interfaces.d/*
```

 and instead add following:
```
auto eth0
iface eth0 inet dhcp

```
close nano with ctrl + X ENTER

14. Close your terminal window.

15. Eject your sdcard from your computer and insert into your RPi

16, connect a ethernet cable to your RPi and router/modem and at last connect your power adapter to your RPI.

17. Go inside your router and search for a device connected with cable and look up the ip of your pi now you can probably ssh into your RPI and give it access to your wifi instead.
18. Good Luck 


