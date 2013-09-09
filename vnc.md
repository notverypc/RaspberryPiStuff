##VNC - Installation##

Install tight VNC: ```sudo apt-get install tightvncserver```  
Run the program: ```tightvncserver```  
Start a VNC session: ```vncserver :1 -geometry 1024x728 -depth 24```  

##VNC - Autostart##
Use this command to create the required file: ```sudo nano /etc/init.d/tightvncserver```   
   
Then copy this:   
```
# First configure the user you want to run this under - this will generally be pi, unless you've created your own users
export USER='pi'

eval cd ~$USER

# Check the state of the command - this'll either be start or stop 
case "$1" in
  start)
    # if it's start, then start vncserver using the details below
    su $USER -c '/usr/bin/vncserver :1 -geometry 1024x768 -depth 16 -pixelformat rgb565'
    echo "Starting vncserver for $USER "
    ;;
  stop)
    # if it's stop, then just kill the process
    pkill Xtightvnc
    echo "vncserver stopped"
    ;;
  *)
    echo "Usage: /etc/init.d/vncserver {start|stop}"
    exit 1
    ;;
esac
exit 0
```  
   
Use this command to set the correct permissions:   ```sudo chmod 755 /etc/init.d/tightvncserver```  

Add file to startup sequence:   ```sudo update-rc.d tightvncserver defaults```

##VNC - Finder_Pi##

If you are a Mac user then you will probably be used to seeing other Macs in the network automatically show up in the Finder, so that you can log on to them and browse the file system or even remote control them.
The Finder_Pi code will do that for the Pi
