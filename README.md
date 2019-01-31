Work in progress. Not ready for stable use yet.

Only tested on Arch Linux (Arm) with a Silvercrest® SIRD14D1 at the moment.


What is it?  
-----------------------------------
A proof of concept of a POSIX shell implementation to control a netradio based on 
the Frontier Silicon® Jupiter/Venice 6.5 module via fsapi.


Which POSIX standard does it follow?
-----------------------------------
It tries to follow the IEEE Std 1003.1™-2017 standard.  
https://pubs.opengroup.org/onlinepubs/9699919799/


What have to do?  
-----------------------------------
Make the main script with `chmod a+x fsradio` executable and cross the fingers it works.


Requirements:
------------------------------------
* A Frontier Silicon® Wi-Fi Radio
* For additional dependencies take a look into dependencies.json


Known issues:   
------------------------------------
* It is too slow
* No manual available at the moment.
* Not an issue of the script, but if you use systemd-resolved with the option `[!UNAVAIL=return]` 
in the /etc/nsswitch.conf, it will prohibit to resolve a hostname. That makes no sense in my opinion. Remove it.


Similar projects:   
------------------------------------
* Frontier Silicon API for PHP: 
https://github.com/flammy/fsapi
* Frontier Silicon API for Python: 
https://github.com/tiwilliam/fsapi
* Frontier Silicon API for .NET: 
https://github.com/z1c0/FsApi
* Frontier Silicon Radio Binding for openHAB: 
https://github.com/openhab/openhab1-addons/wiki/Frontier-Silicon-Radio-Binding
