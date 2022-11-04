# Network Reconnaissance

## ARP Table

Viewing the ARP table can provide good passive information about active clients on the same network.

```
arp -an
```

## Routing Table

The routing table for devices can tell you the default gateway and any static routes for the device.

### Linux

```
route -n
```

### FreeBSD/Solaris

```
route -n [get default]
```

### All Nix Variants

```
netstat -nr
```

## Active Network Connections

Understanding active network connections can give you a lot of information about listening services on the system as well as any current connections to or from a remote system.

### Linux

```
netstat -plantu
```

### Solaris

```
netstat -an
```

### FreeBSD

```
sockstat
```

## DNS Servers Used

Understanding any manually set DNS servers can be useful in enumerating local DNS servers that are resolving local domain names.

```
cat /etc/resolv.conf
```

!!!
***Note:*** For machines using NetworkManager, you can use the following command to find DNS servers in use: `nmcli c show "<nic name>" | grep dns`
!!!