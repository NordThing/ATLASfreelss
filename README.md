# REWORK of ATLAS 3D scanner

ATLAS 3D scanner files - both for hardware and software and 3d printing files collected on one place.
Will make total rework of the ATLAS 3D scanner.

A link for assembling https://youtu.be/TEsBM5ACriQ 
and one more https://www.youtube.com/watch?v=awtLSCLJ3qs

Calibration video https://youtu.be/vvfXvUgtoUg

# FreeLSS

FreeLSS is a laser scanning program for the Raspberry Pi. It allows a Raspberry Pi to function as the core to a complete turn table laser scanning system.



### COMPILE

These instructions assume you are running the latest version of Raspbian.  Other distros will likely require changes.

First, update the firmware to the latest version and reboot.
```
$ sudo apt-get update
$ sudo apt-get upgrade
```

Install the dependencies that are managed by the package manager.
```
$ sudo apt-get install libpng-dev libjpeg-dev git-core gcc build-essential unzip sqlite3 libsqlite3-dev libmicrohttpd-dev libcurl4-openssl-dev libiw-dev libssl-dev wiringpi 
```

Download and build FreeLSS
```
$ git clone https://github.com/hairu/freelss
$ cd freelss
$ make
```
### Running FreeLSS
FreeLSS must be ran as root (or another user with access to the hardware pins).  The interface for FreeLSS is web based and by default runs on port 80.  When running, access it by navigating to http://localhost/ from the Raspberry Pi itself. Or access it from another machine on the network by the Raspberry Pi's IP or hostname.  For Example: http://raspberrypi/

The following command starts FreeLSS.
```
$ cd src
$ sudo ./freelss
```

The following command automatically starts FreeLSS everytime the Raspberry Pi is powered on.
```
$ make startup
```
