pdee@pdee:~$ sudo virsh
[sudo] password for pdee:
Welcome to virsh, the virtualization interactive terminal.

Type:  'help' for help with commands
       'quit' to quit

virsh # exit

pdee@pdee:~$ sudo virsh net-dumpxml default
<network>
  <name>default</name>
  <uuid>0982f516-c593-40c0-940e-15716d551733</uuid>
  <forward mode='nat'>
    <nat>
      <port start='1024' end='65535'/>
    </nat>
  </forward>
  <bridge name='virbr0' stp='on' delay='0'/>
  <mac address='52:54:00:4e:e5:01'/>
  <ip address='192.168.122.1' netmask='255.255.255.0'>
    <dhcp>
      <range start='192.168.122.2' end='192.168.122.254'/>
    </dhcp>
  </ip>
</network>

pdee@pdee:~$ sudo virsh net-dumpxml wan_bridge
error: failed to get network 'wan_bridge'
error: Network not found: no network with matching name 'wan_bridge'

pdee@pdee:~$ sudo virsh net-list
 Name      State    Autostart   Persistent
--------------------------------------------
 default   active   yes         yes

pdee@pdee:~$ sudo brctl show
bridge name	bridge id		STP enabled	interfaces
br-64de553e2350		8000.b228aa5a2aa8	no
br0		8000.525400dbf8fe	no		enp2s0
docker0		8000.7631e7e6a285	no
virbr0		8000.5254004ee501	yes
p