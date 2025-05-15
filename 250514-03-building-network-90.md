# ... migrating blk 10.10.89.94 ... to new network 10.10.90. ...

<pre>
blk will become the pfsense router
wan ip 173.166.130.90
lan ip 10.10.90.1
</pre>

# blk 89.94 hardware stats
## mother board NIC
<pre>
blk@blk:~$ sudo lshw -class network
  *-network
       description: Ethernet interface
       product: 82579LM Gigabit Network Connection (Lewisville)
       vendor: Intel Corporation
       physical id: 19
       bus info: pci@0000:00:19.0
       logical name: eno1
       version: 04
       serial: 74:46:a0:a2:13:6a
       size: 1Gbit/s
       capacity: 1Gbit/s
       width: 32 bits
       clock: 33MHz
       capabilities: pm msi bus_master cap_list ethernet physical tp 10bt 10bt-fd 100bt 100bt-fd 1000bt-fd autonegotiation
       configuration: autonegotiation=on broadcast=yes driver=e1000e driverversion=6.8.0-52-generic duplex=full firmware=0.13-4 ip=10.10.89.94 latency=0 link=yes multicast=yes port=twisted pair speed=1Gbit/s
       resources: irq:25 memory:f7c00000-f7c1ffff memory:f7c39000-f7c39fff ioport:f080(size=32)
</pre>


<pre>
steps ...
</pre>

# addded USB Ethernet interface
<pre>
blk@blk:~$ sudo lshw -class network -short
H/W path         Device           Class          Description
============================================================
/0/100/19        eno1             network        82579LM Gigabit Network Connection (Lewisville)
/4               enx7cf17ed9785c  network        Ethernet interface
</pre>