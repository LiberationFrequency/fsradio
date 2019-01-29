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


Requirements:
------------------------------------
* A Frontier Silicon® Wi-Fi Radio
* For additional dependencies take a look into dependencies.json


ToDo:   
------------------------------------


Known issues:   
------------------------------------
* Too slow
* No manual available at the moment.
* Not an issue of the script, but if you use systemd-resolved with the option `[!UNAVAIL=return]` 
in the /etc/nsswitch.conf, it will prohibit to resolve a hostname. That makes no sense in my opinion. Remove it.
* Signal quality of FM is an octet, but should be in percent.
