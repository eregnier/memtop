# Memtop

A top for memory

Yes I needed it for real clean memory understanding. I find top and htop unclear for memory information so I did this from a lost command on the internet that works pretty neat.

I added a sort and a less for top like features

## Installation

```bash
sudo curl -s "https://raw.githubusercontent.com/eregnier/memtop/master/memtop" -o /usr/local/bin/memtop && sudo chmod +x /usr/local/bin/memtop && echo -e '\e[32m[OK]\e[0m memtop installed' || echo -e '\e[31m[KO]\e[0m memtop install error'
```

## Usage

```bash
memtop
```

output looks like

```bash
    99.441406 Mb containerd-shim -namespace moby -workdir /var/lib/containerd/io.containerd.runtime.v1.linux/moby/d70e7571dabe619b3556e1cbf537732027ddbf486aeea07b673975a7effb9f05 -address /run/containerd/containerd.sock -containerd-binary /usr/bin/containerd -runtime-root /var/run/docker/runtime-runc
    92.062500 Mb /usr/bin/flameshot
     9.085938 Mb bash
     9.085938 Mb bash
     8.945312 Mb /usr/sbin/thermald --no-daemon --dbus-enable
     8.816406 Mb /lib/systemd/systemd-timesyncd
     8.679688 Mb /usr/sbin/irqbalance --foreground
     8.582031 Mb bash
     8.582031 Mb bash
     # [...]
```

This will display your memory usage sorted with vim like search feature (type / and search token and hit "enter")

for something even more like htop with real time refresh, do something like

```bash
watch -n 0.5 memtop
```

and for a particular process you might grep the whole thing

```bash
watch -n 0.5 'memtop | grep python | grep -v grep'
```

```bash
Every 0,5s: memtop | grep python | grep -v grep        Scorpion: Sat Dec 12 15:14:36 2020

     8.054688 Mb /usr/bin/python3 /usr/bin/networkd-dispatcher --run-startup-triggers
    57.621094 Mb /usr/bin/python3 /usr/bin/blueman-applet
    51.261719 Mb /usr/bin/python3 /usr/bin/blueman-tray
     2.816406 Mb python /tmp/mem.py
    16.281250 Mb /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
```
