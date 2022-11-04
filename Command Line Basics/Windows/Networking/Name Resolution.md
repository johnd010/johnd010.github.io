# Name Resolution

Windows uses Name Resolution for various aspects of it's networking and domain services. Some of the ways it does this name resolution include via Domain Name System (DNS), NetBIOS, and Link-Local Multicast Name Resolution (LLMNR).

When Windows resolves a hostname the priority/order for resolutions follows the following order:

1. Check if the hostname is the same as self
2. Check the local DNS hosts file `C:\Windows\System32\drivers\etc\hosts` for a name
3. Query the network DNS server(s)
4. Perform a NetBIOS lookup, which follows the following process:
    4a. Check the local LMHOSTS file
    4b. Check the existing NetBIOS cache
    4c. Do a NetBIOS network lookup

## DNS

DNS is the most widely used resolution protocol.

### Query a DNS server for a specific host

```
nslookup <server> <host>
```

### Attempt a DNS Zone Transfer

```
nslookup
...
server X.X.X.X
...
ls -d <domain name> 
```

## NetBIOS

NetBIOS can resolve hostnames to IP addresses.

NetBIOS is commonly enabled in Windows environments by default, but is often used less than DNS (because of DNS's more robust features).

NetBIOS hostnames are capped at 15 bytes.

### View NetBIOS Cache

```
`nbtstat -c`
```

### Resolve an IP Address using NetBIOS

```
nbtstat -A X.X.X.X
```

### Resolve a Hostname using NetBIOS

```
nbtstat -a <hostname>
```


## LLMNR

LLMNR builds on DNS and allows for performing name resolution in a broadcast fashion. It  was first implemented in Windows Vista.

LLMNR is enabled by default on Windows hosts.

You can resolve a hostname manually via LLMNR with PowerShell via: `Resolve-DnsName –LlmnrOnly <hostname>`

!!!
Note: ARP, NetBIOS, and LLMNR all share a common flaw: the response is not validated, and any malicious machine can respond to broadcasts with their own information . This can lead to man-in-the-middle attacks or credential sniffing.
!!!