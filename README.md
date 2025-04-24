# Jetstream2
ACCESS-CI and JetStream2 Use

## ACCESS-CI & Getting into Jetstream:

Get an ACCESS-CI XSEDE login: https://access-ci.org/  
Ask Hugo to add you to our project. You can stay updated on where our tokens are spent, our users, etc [here](https://allocations.access-ci.org/)  

Get Exosphere, the GUI app for interacting with the system -- Jetstream has good documentation, read about it [here](https://docs.jetstream-cloud.org/ui/exo/exo/)
You can find our allocation on Jetstream [here](https://jetstream2.exosphere.app/exosphere/), and if you do not:
````
>> Click "Add allocation", and connect your ACCESS account
````

## Exosphere: 
Exosphere has a few important things to interact with. This is just an overview and I highly recommend reading Jetstream's documentation. 
### INSTANCE (basically our fake computer in Indiana on Jetstream2!)
This is useful to check on, and make sure that things are correct - AS A COURTESY :: Please SHELVE THE INSTANCE if you're done using it.   


To interact and change things in the instance, go to "Actions" button in the top right corner, this gives you master meta-control. To actually USE the instance: 
1. Guacamole -- Has a WEB SHELL (interactive CMD prompt) and a WEB DESKTOP (an emulated fake desktop in Ubuntu24 for our use)
2. The CONSOLE -- important for interacting with the base system, getting and giving permissions, security settings, etc...
You can always create a new instance! This can be very useful to you, personalized, etc...

#### Instance Credentials
Instances each come with a set of credentials (a private IP address, **00.00.00.00**, and your username, **exouser**). These are used in console and WinSCP to interact with the instance. 

### VOLUMES (basically virtual USB drives)
This can contain data to load, save, and transfer from the instance. It is very useful, especially when uploading videos, pre-made scripts, etc...  
I recommend downloading [WinSCP](winscp.net) if you have a Windows computer -- this will allow you to transfer files in and out of your volume.
Volumes are mounted to /media/volume/urVolumeName and will have a location like /dev/sdb. 
To increase the size of a volume in GB, you must use Horizon -- look into that [here](https://docs.jetstream-cloud.org/ui/horizon/intro/). The information on how to increase the size of a volume is [here](https://docs.jetstream-cloud.org/general/volume/#backup-exporting)   

#### WinSCP & Volumes
To load and unload things via WinSCP to the volume, load into WinSCP. It should prompt you to log in, if not click 'New Tab' in the top. Using file protocol **SCP** and host name 00.00.00.00 (our instance credential private IP) and username (usually exouser). Put in the password for exouser that is given in the credentials tab of our instance (copy and paste this into WinSCP).  
Then, you should see the user directory **/home/exouser** or something of the sort on the RIGHT side, and your local directory on the LEFT side. This has ~60GB of space on the m3.xl allocation I usually use, which is quite large. Pretty good space for downloading things and moving them to volumes, but definitely not storage space. This will also get whiped if we ever delete the instance (not the case for Volumes).   
You can see your home directory on the WEB DESKTOP through Exosphere and go to the file explorer app. Any attached volumes will be under "Other Locations", where you can click and find them. 

In order to *load things directly to a volume with WinSCP*, you have to navigate to /media/volume/YOURVOLUME. This can be done by clicking the directory of the virtual computer on the right side, right above the 'Name' column identifier.  
Change to /media/volume/YOURVOLUME, and then you can load straight in and out.  

If you have problems, follow [this linked document](https://github.com/Samineni-Lab/Jetstream2/wiki/Volumes#debugging)
### PUBLIC IP ADDRESS
This can be thought of as the location of the virtual computer, and is one way you get in and out. You can add and use public IP addresses to get in and out of the instance more easily from outside of Jetstream2, if this is desirable (i.e, Jetstream2 doesn't do something you want it to for back-end control)  

### SSH, Public Keys
This can be thought of as the key to the computer, and is how you will interact with the public IP address. In things like winSCP, the exouser@00.00.00.00 is the IP that will be public for public in/out privileges, but we don't usually use these.




