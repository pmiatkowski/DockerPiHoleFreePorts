# Pi-Hole inside Docker - unblocked ports, physical IP & MAC addresses

Simulate Pi-Hole as a separate device connected to your network with it's own IP and MAC addresses and runing inside container.



### Thanks to Tony Lawrence:

http://tonylawrence.com/posts/unix/synology/running-pihole-inside-docker/

http://tonylawrence.com/posts/unix/synology/free-your-synology-ports/

# How to
1. Edit *docker-compose.yaml* file and set your new IP address - this can be anything.

Update:
```
ipv4_address: 192.168.1.XXX
```

2. Edit *dns/docker-compose.yaml* file

Update to match your PI's IP inside local network (cmd: **ifconfig**):
```
ServerIP: 192.168.1.YYY
```

3. Edit *dns/config/dnsmasq.conf* file:

Update - same IP as in step 2.
```
address=/pihole/192.168.1.YYY
```

4. Edit *dns/config/hosts* file

Update - same IP as in step 2. and 3.
```
192.168.1.YYY pihole
```
