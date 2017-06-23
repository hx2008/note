Upgrade kernal
```
root@cloud:~# apt-cache search linux-image
root@cloud:~# apt-get install linux-image-4.10.0-25-generic
root@cloud:~# apt-get install linux-image-extra-4.10.0-25-generic
root@cloud:~# apt-get install linux-headers-4.10.0-25-generic
```
Reboot
```
root@cloud:~# uname -r
4.10.0-25-generic
```
Enable BBR
```
root@cloud:~# echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
root@cloud:~# echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
root@cloud:~# sysctl -p
net.core.default_qdisc = fq
net.ipv4.tcp_congestion_control = bbr
root@cloud:~# sysctl net.ipv4.tcp_available_congestion_control
```
