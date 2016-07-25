tsocks-macosx
=============

tsocks 1.8 with the mac osx patch

----

**For Mac OS X 10.11(El Capitan) and newer, we need to put bin and lib into /usr/local/bin and /usr/local/lib separately, instead of /usr/bin and /usr/lib, since /usr/bin and /usr/lib are protected by System Integrity Protection of the new OS.**

####Download & Install it

Download source into dir tsocks-macosx, and then

    cd tsocks-macosx

    autoconf

    ./configure --exec_prefix=/usr/local

    make

    sudo cp tsocks /usr/local/bin

    sudo cp libtsocks.dylib.1.8 /usr/local/lib
    sudo ln -s /usr/local/lib/libtsocks.dylib.1.8 /usr/local/lib/libtsocks.dylib

    sudo cp tsocks.conf.simple.example /etc/tsocks.conf
  

NOTE: **please modify your _/etc/tsocks.conf_ according to your local environment.**

If you're running a SSH tunnel a server locally, a typical tsocks.conf looks like:

```
# We can access 192.168.0.* directly
local = 192.168.0.0/255.255.255.0

# Otherwise we use the server
server = 127.0.0.1
server_type = 5
server_port = 1080
```

----

####Reference: 

  - [1. tsocks-1.8] (http://sourceforge.net/projects/tsocks/)
  - [2. macosx-patch] (http://marc-abramowitz.com/download/tsocks-1.8_macosx.patch)
