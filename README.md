RaspberryPiStuff
================

Collection of Scripts and Stuff I use with my Pi

##VNC - Installation##

Install tight VNC: ```sudo apt-get install tightvncserver```  
Run the program: ```tightvncserver```  
Start a VNC session: ```vncserver :1 -geometry 1024x728 -depth 24```  

##VNC - Autostart##
Use this command to create the required file:  
```sudo nano /etc/init.d/tightvncserver```   
Then copy the contents of tightvncserver file.  
Use this command to set the correct permissions:   
```sudo chmod 755 /etc/init.d/tightvncserver```  

Then copy the contents of the tightvncserver

##VNC - Finder_Pi##

If you are a Mac user then you will probably be used to seeing other Macs in the network automatically show up in the Finder, so that you can log on to them and browse the file system or even remote control them.
The Finder_Pi code will do that for the Pi
