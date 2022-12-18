ShadowsocksR
===========

[![Build Status]][Travis CI]

A fast tunnel proxy that helps you bypass firewalls.

Server
------

### Install with one click (一键安装)
```
sudo su

wget --no-check-certificate https://raw.githubusercontent.com/ShadowsocksR-Live/shadowsocksr/manyuser/ssr-install.sh

chmod +x ssr-install.sh

./ssr-install.sh 2>&1 | tee ssr-install.log
```
To uninstall, using
```
./ssr-install.sh uninstall
```

### Install

Please make you as `root` account and change your working directory to the root first.

    sudo su
    cd / 

Debian / Ubuntu:

    apt-get install git
    git clone https://github.com/ShadowsocksR-Live/shadowsocksr.git

CentOS:

    yum install git
    git clone https://github.com/ShadowsocksR-Live/shadowsocksr.git

Windows:

    git clone https://github.com/ShadowsocksR-Live/shadowsocksr.git

### Usage for single user on linux platform

If you clone it into "/shadowsocksr" folder, 
please enter "/shadowsocksr" first, 

    cd /shadowsocksr

then run:

    bash initcfg.sh

Now, move to "/shadowsocksr/shadowsocks", 

    cd /shadowsocksr/shadowsocks

then run:

    python server.py -p 443 -k password -m aes-128-cfb -O auth_aes128_md5 -o tls1.2_ticket_auth_compatible

Check all the options via `-h`.

You can also use a configuration file instead (recommend), move to "/shadowsocksr" and edit the file "user-config.json" with `vi` text editor, 

    vi /shadowsocksr/user-config.json

then move to "/shadowsocksr/shadowsocks" again, 

    cd /shadowsocksr/shadowsocks

and just run:

    python server.py

Now. Mission completed.

To run in the background:

    ./logrun.sh

To stop:

    ./stop.sh

To monitor the log:

    ./tail.sh

### Run as an automatical service

If you hope the remote host to start the shadowsocksr service automatically when the host started, please:

Edit the configuration file "user-config.json" with `vi` text editor, modify it with correct parameters.

    vi /shadowsocksr/user-config.json

Edit `/etc/rc.local` file with `vi` editor,

    vi /etc/rc.local

and add the following command to the end of the `/etc/rc.local` file.

    /shadowsocksr/shadowsocks/logrun.sh
    
If the first line of file `/etc/rc.local` is not `#!/bin/sh -e`, please add it to the first line, 
then make `/etc/rc.local` executable using the following command:

    chmod +x /etc/rc.local
    
Please `reboot` your linux computer and all is done.

About editing `user-config.json` and `/etc/rc.local` files with `vi` text editor utility, please see [How to Use the vi Editor](https://www.washington.edu/computing/unix/vi.html).


Client
------

* [Windows] / [macOS]
* [Android] / [iOS]
* [OpenWRT]

Use GUI clients on your local PC/phones. Check the README of your client
for more information.

Documentation
-------------

You can find all the documentation in the [Wiki].

License
-------

Copyright 2015 clowwindy

Licensed under the Apache License, Version 2.0 (the "License"); you may
not use this file except in compliance with the License. You may obtain
a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations
under the License.

Bugs and Issues
----------------

* [Issue Tracker]



[Android]:           https://github.com/shadowsocksr/shadowsocksr-android
[Build Status]:      https://travis-ci.org/shadowsocksr/shadowsocksr.svg?branch=manyuser
[Debian sid]:        https://packages.debian.org/unstable/python/shadowsocks
[iOS]:               https://github.com/shadowsocks/shadowsocks-iOS/wiki/Help
[Issue Tracker]:     https://github.com/shadowsocksr/shadowsocksr/issues?state=open
[OpenWRT]:           https://github.com/shadowsocks/openwrt-shadowsocks
[macOS]:             https://github.com/shadowsocksr/ShadowsocksX-NG
[Travis CI]:         https://travis-ci.org/shadowsocksr/shadowsocksr
[Windows]:           https://github.com/shadowsocksr/shadowsocksr-csharp
[Wiki]:              https://github.com/breakwa11/shadowsocks-rss/wiki
