## vultr.com


# skysilk.com


# virmach.com

---

测试脚本：https://bench.sh/

```
[root@skysilk ~]# wget -qO- bench.sh | bash
----------------------------------------------------------------------
CPU model            : Intel(R) Xeon(R) CPU E5-2697 v2 @ 2.70GHz
Number of cores      : 1
CPU frequency        : 2992.924 MHz
Total size of Disk   : 9.8 GB (0.8 GB Used)
Total amount of Mem  : 512 MB (78 MB Used)
Total amount of Swap : 512 MB (0 MB Used)
System uptime        : 0 days, 0 hour 25 min
Load average         : 21.82, 22.81, 23.38
OS                   : CentOS 7.3.1611
Arch                 : x86_64 (64 Bit)
Kernel               : 4.15.18-9-pve
----------------------------------------------------------------------
I/O speed(1st run)   : 3.3 MB/s
I/O speed(2nd run)   : 3.7 MB/s
I/O speed(3rd run)   : 4.1 MB/s
Average I/O speed    : 3.7 MB/s
----------------------------------------------------------------------
Node Name                       IPv4 address            Download Speed
CacheFly                        205.234.175.175         23.7MB/s
Linode, Tokyo, JP               106.187.96.148          2.75MB/s
Linode, Singapore, SG           139.162.23.4            3.83MB/s
Linode, London, UK              176.58.107.39           6.28MB/s
Linode, Frankfurt, DE           139.162.130.8           9.36MB/s
Linode, Fremont, CA             50.116.14.9             16.4MB/s
Softlayer, Dallas, TX           173.192.68.18           15.9MB/s
Softlayer, Seattle, WA          67.228.112.250          21.2MB/s
Softlayer, Frankfurt, DE        159.122.69.4            13.3MB/s
Softlayer, Singapore, SG        119.81.28.170           13.9MB/s
Softlayer, HongKong, CN         119.81.130.170          15.0MB/s
----------------------------------------------------------------------
```

```
[root@JumboMellow-VM ~]# wget -qO- bench.sh | bash
----------------------------------------------------------------------
CPU model            : QEMU Virtual CPU version (cpu64-rhel6)
Number of cores      : 1
CPU frequency        : 2999.998 MHz
Total size of Disk   : 9.6 GB (1.6 GB Used)
Total amount of Mem  : 236 MB (150 MB Used)
Total amount of Swap : 255 MB (43 MB Used)
System uptime        : 0 days, 0 hour 1 min
Load average         : 1.76, 0.70, 0.26
OS                   : CentOS 7.6.1810
Arch                 : x86_64 (64 Bit)
Kernel               : 3.10.0-693.11.6.el7.x86_64
----------------------------------------------------------------------
I/O speed(1st run)   : 236 MB/s
I/O speed(2nd run)   : 270 MB/s
I/O speed(3rd run)   : 247 MB/s
Average I/O speed    : 251.0 MB/s
----------------------------------------------------------------------
Node Name                       IPv4 address            Download Speed
CacheFly                        205.234.175.175         37.5MB/s
Linode, Tokyo, JP               106.187.96.148          3.96MB/s
Linode, Singapore, SG           139.162.23.4            3.11MB/s
Linode, London, UK              176.58.107.39           8.86MB/s
Linode, Frankfurt, DE           139.162.130.8           7.18MB/s
Linode, Fremont, CA             50.116.14.9             4.94MB/s
Softlayer, Dallas, TX           173.192.68.18           14.2MB/s
Softlayer, Seattle, WA          67.228.112.250          7.97MB/s
Softlayer, Frankfurt, DE        159.122.69.4            6.59MB/s
Softlayer, Singapore, SG        119.81.28.170           2.79MB/s
Softlayer, HongKong, CN         119.81.130.170          2.94MB/s
----------------------------------------------------------------------
```