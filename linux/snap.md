Centos 系统上安装：https://docs.snapcraft.io/installing-snap-on-centos/10020

```
$ yum install -y snapd

$ snap version
snap    2.38-1.el7
snapd   unavailable
series  -

$ systemctl enable --now snapd.socket
Created symlink from /etc/systemd/system/sockets.target.wants/snapd.socket to /usr/lib/systemd/system/snapd.socket.

$ snap version
snap    2.38-1.el7
snapd   2.38-1.el7
series  16
centos  7
kernel  3.10.0-957.1.3.el7.x86_64

$ ln -s /var/lib/snapd/snap /snap
```