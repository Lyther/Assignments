# Lab13 Practice Writeup

This solution manual would be useful tomorrow.

----

## Practice 1

1. The yellow spot means there is circle in the network, if the shortest path won't through yellow spot, then the connection can be established. Otherwise, the connection would timeout.
	* However, if there is one path without yellow spot, then the connection can be established through that route.

2. The root of spanning-tree is Switch0, use command `show spanning-tree` and find it in Root ID.

3. Yes, yellow spot disappeared. The connection won't be blocked.

4. Use command `spanning-tree vlan 1 root primary` in config page.

## Practice 2

Use this sequence of command to configure vlan 10 and vlan 20:

```bash
enable
configure terminal
vlan 10
exit
interface fastEthernet 0/1
switchport access vlan 10
exit
```

Notice that vlan number can be 10 or 20, and the ethernet port can be 0/1, 0/2, and 0/3.
Then use following command to show vlan status:

```bash
show vlan brief
```

1. PCs in the same VLAN could communicate with each other.

2. The configuration steps for multilayer as follow:

```bash
interface fastEthernet 0/1
switchport trunk encapsulation dot1q
switchport mode trunk
exit
```

The ethernet port should be 0/1 and 0/2, and set following vlan:

```bash
interface vlan10
ip address 192.168.10.254 255.255.255.0
exit
```

The vlan number should be 10 and 20, and ip address should be distingushable.

Then set the default gateway for PCs to ip address of multilayer.

Set them for both switches. Try conenction success.