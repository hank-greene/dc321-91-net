
https://www.server-world.info/en/note?os=Ubuntu_24.04&p=kvm&f=1


# context .........
pdee@pdee:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp2s0: <BROADCAST,MULTICAST,PROMISC,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 78:45:c4:2f:b8:1e brd ff:ff:ff:ff:ff:ff
    inet 10.10.91.12/24 brd 10.10.91.255 scope global enp2s0
       valid_lft forever preferred_lft forever
    inet6 fe80::7a45:c4ff:fe2f:b81e/64 scope link
       valid_lft forever preferred_lft forever
3: br-64de553e2350: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether b2:28:aa:5a:2a:a8 brd ff:ff:ff:ff:ff:ff
    inet 172.18.0.1/16 brd 172.18.255.255 scope global br-64de553e2350
       valid_lft forever preferred_lft forever
4: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether 76:31:e7:e6:a2:85 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
5: virbr0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    link/ether 52:54:00:4e:e5:01 brd ff:ff:ff:ff:ff:ff
    inet 192.168.122.1/24 brd 192.168.122.255 scope global virbr0
       valid_lft forever preferred_lft forever

# ........
pdee@pdee:~$ sudo cat /etc/netplan/50-cloud-init.yaml
network:
  version: 2
  ethernets:
    enp2s0:
      addresses:
      - "10.10.91.12/24"
      nameservers:
        addresses:
        - 75.75.75.75
        - 75.75.76.76
        search:
        - 75.75.75.75
        - 75.75.76.76
      routes:
      - to: "default"
        via: "10.10.91.1"


# ........
pdee@pdee:~$ sudo cat /etc/netplan/01-netcfg.yaml
network:
  ethernets:
    enp2s0:
      dhcp4: false
      # disable existing configuration for ethernet
      #addresses: [10.0.0.30/24]
      #routes:
      #  - to: default
      #    via: 10.0.0.1
      #    metric: 100
      #nameservers:
      #  addresses: [10.0.0.10]
      #  search: [srv.world]
      dhcp6: false
  # add configuration for bridge interface
  # [macaddress] ⇒ specify HW address of enp1s0
  bridges:
    br0:
      interfaces: [enp2s0]
      dhcp4: false
      addresses: [10.10.91.12/24]
      macaddress: 52:54:00:db:f8:fe
      routes:
        - to: default
          via: 10.10.91.1
          metric: 100
      nameservers:
        addresses: [75.75.75.75,75.75.76.76]
        search: [75.75.75.75,75.75.76.76]
          #search: [srv.world]
      parameters:
        stp: false
      dhcp6: false
  version: 2


$ sudo netplan apply
[sudo] password for pdee:

** (generate:67792): WARNING **: 13:28:46.309: Permissions for /etc/netplan/01-netcfg.yaml are too open. Netplan configuration should NOT be accessible by others.

** (process:67790): WARNING **: 13:28:46.662: Permissions for /etc/netplan/01-netcfg.yaml are too open. Netplan configuration should NOT be accessible by others.

** (process:67790): WARNING **: 13:28:46.843: Permissions for /etc/netplan/01-netcfg.yaml are too open. Netplan configuration should NOT be accessible by others.



# 
pdee@pdee:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp2s0: <BROADCAST,MULTICAST,PROMISC,UP,LOWER_UP> mtu 1500 qdisc fq_codel master br0 state UP group default qlen 1000
    link/ether 78:45:c4:2f:b8:1e brd ff:ff:ff:ff:ff:ff
    inet 10.10.91.12/24 brd 10.10.91.255 scope global enp2s0
       valid_lft forever preferred_lft forever
3: br-64de553e2350: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether b2:28:aa:5a:2a:a8 brd ff:ff:ff:ff:ff:ff
    inet 172.18.0.1/16 brd 172.18.255.255 scope global br-64de553e2350
       valid_lft forever preferred_lft forever
4: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default
    link/ether 76:31:e7:e6:a2:85 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
5: virbr0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    link/ether 52:54:00:4e:e5:01 brd ff:ff:ff:ff:ff:ff
    inet 192.168.122.1/24 brd 192.168.122.255 scope global virbr0
       valid_lft forever preferred_lft forever
6: br0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 52:54:00:db:f8:fe brd ff:ff:ff:ff:ff:ff
    inet 10.10.91.12/24 brd 10.10.91.255 scope global br0
       valid_lft forever preferred_lft forever
    inet6 fe80::5054:ff:fedb:f8fe/64 scope link
       valid_lft forever preferred_lft forever

