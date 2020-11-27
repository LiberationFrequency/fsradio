Work in progress. Not ready for stable use yet.

Only tested on Arch Linux (Arm)(both 64bit) with a Silvercrest® SIRD14C2, SIRD14C4, SIRD14D1, SIRD14E1 at the moment.


What is it?  
-----------------------------------
A proof of concept of a POSIX shell implementation to control a netradio based on 
the Frontier Silicon® Jupiter/Venice 6.5 module via fsapi.


Which POSIX standard does it follow?
-----------------------------------
It tries to follow the IEEE Std 1003.1™-2017 standard.  
https://pubs.opengroup.org/onlinepubs/9699919799/


What I have to do?  
-----------------------------------
Make the main script with `chmod +x fsradio` executable and cross your fingers that it works.  

For Archlinux there is a PKGBULD in progress. You can found it in this package and at:  
https://github.com/LiberationFrequency/PKGBUILDs/tree/master/NonAUR/testing/fsradio-git  
curl -LJO https://raw.githubusercontent.com/LiberationFrequency/PKGBUILDs/master/NonAUR/testing/fsradio-git/PKGBUILD


Requirements:
------------------------------------
* A Frontier Silicon® Wi-Fi Radio
* For additional dependencies take a look into share/fsdata/dependencies.json or execute ./fsradio --checkdep


Known issues:   
------------------------------------
* '...play ch xx' does not fit together with 'play ch list'. It uses the sequence instead the item key.  
* '...play ch list' does not work on SIRD14E3 at all.  
* '...date show' shows +-offset for a negative offset and lack a zero. 
* The timesync of DAB switch intern to FM. The uncertainty of FM is +/- 200ms and DAB is a stratum2 with +/- 40ms.
* There is something wrong with the API and the internal timesync. That does not fit together. Set it manually to DAB!
* '...info notifies' closes after receiving an event, but the socket should remain open.
* '...play stream URI' produces a lot of UPnP error, although it should work. Some streams will force the device to reboot.
* '...eq bass/treb x' does not interact with the radio IR remote. That is not an issue of the script. The radio itself does not write the value into custom paramX.
* (fixed temporary)'...info net' converts the SSID array not correct to a string in some shells.
* It is too slow.
* No manual available at the moment.
* Not an issue of the script, but if you use systemd-resolved with the option `[!UNAVAIL=return]` 
in the /etc/nsswitch.conf, it will prohibit to resolve a hostname in the local net. In my opinion this makes no sense. 
You can remove it or use e.g. glibc for resolving. I think removing is the minimally invasive way.


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
* Frontier Silicon Module for FHEM:  
https://github.com/mumpitzstuff/fhem-SIRD
