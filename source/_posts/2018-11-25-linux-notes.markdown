---
layout: post
title:  "Linux Notes!"
date:   2018-11-24 13:46:52
comments: true
image: /images/linux.jpeg
categories: 
---

### To see the path of any command

**which**
ex. - which java
/usr/bin/java

----

### To see the dependencies of any binary

**ldd**

ldd /bpcd

Nm -C

----

find . -name "*.*" `|` xargs grep -i "cli"

find /net/rmnbpt/results/NB/2016_07/285479 -name catalina.out  `|` xargs grep "org.apache.catalina.startup.Catalina.start Server startup in" `|` awk '{print $9}'

find . `|` xargs grep "texthere" *

tail -f 51216-111-1664864778-180625-0000000000.log `|` grep -i query

df -k

ps -eaf| grep bpcompat | awk  '{print $2}' | xargs kill -9


### Firewall

https://www.cyberciti.biz/faq/fedora-redhat-centos-5-6-disable-firewall/

https://linuxconfig.org/how-to-stop-start-and-disable-enable-firewall-on-redhat-7-linux-system
