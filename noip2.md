Create Folder   
```sudo mkdir noip```

Download and extract No-IP   
```
sudo wget "http://www.no-ip.com/client/linux/noip-duc-linux.tar.gz"   
sudo tar -vzxf noip-duc-linux.tar.gz   
cd noip-2.1.9-1  
sudo make   
sudo make install   
```

Create new file called noip2   
```sudo nano /etc/init.d/noip2```  

Enter the following:
```
#!/bin/sh
### BEGIN INIT INFO
# Provides: noip2
# Required-Start: $remote_fs $syslog
# Required-Stop: $remote_fs $syslog
# Default-Start: 2 3 4 5
# Default-Stop: 0 1 6
# Short-Description: Start daemon at boot time
# Description: Enable service provided by daemon.
### END INIT INFO
case "$1" in
start)
echo "Starting No-IP"
/usr/local/bin/noip2
;;
 
stop)
echo "Stopping No-IP"
killall noip2
;;
 
*)
echo "Usage: /etc/init.d/noip2 {start|stop}"
exit 1
;;
esac
exit 0  
```   

Change the permissions and run at startup:  
```
sudo chmod 755 /etc/init.d/noip2
sudo update-rc.d noip2 defaults
```  

Then reboot the Pi:   
``` sudo reboot ```




