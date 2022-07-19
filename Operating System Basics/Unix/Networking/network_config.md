# Network Configuration Information

`ifconfig [-a]` or `ip a` are the commands that will generally give you basic networking information on a nix machine.

## Persistent Network Information

Across the various nix variants, you can set and view persistent networking configurations via different mechanisms.

### CentOS

```
cat /etc/sysconfig/network-scripts/ifcfg*
```

### Debian

```
cat /etc/network/interfaces
```

### Solaris

```
cat /etc/hostname.<interface>
```

```
cat /etc/inet/ipnodes
```

!!!
***Note:*** You can configure Solaris 11 networking information via: `ipadm` and `dladm`. `ipadm` configures network layer settings. `dladm` configures data-link layer settings.
!!!

### FreeBSD

```
cat /etc/rc.conf
```

### Systems that use NetworkManager

For systems that make use of NetworkManager you can view the devices via:

```
nmcli device
```

Additionally, you can list connections via:

```
nmcli c [show <int>]
```

## NICs

Network Interface Cards (NICs) are typically named in a couple of manners.

### Kernel Naming Scheme

This traditional kernel naming scheme for NICs is unpredictable and is the default if nothing specific is set. 

!!!
***Example:*** eth0
!!!

### On-Board Device Naming Scheme

!!!
***Example:*** eno1
!!!

### PCI Express Naming Scheme

!!!
***Example:*** ens1, enp2s0 (PCI 2, Slot 0)
!!!

### Interface MAC Naming Scheme

!!!
***Example:*** enx78e7d1ea46da
!!!