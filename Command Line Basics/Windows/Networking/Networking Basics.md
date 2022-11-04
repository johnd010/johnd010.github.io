# Windows Networking Basics

## Windows Device Networking Information


`ipconfig` includes information such as Your IPv4 and IPv6 address, your subnet mask, your default gateway, all Network Interface Cards (NICs), etc.

```
ipconfig /all
```

## View DNS Cache (Recent DNS Queries) on the System

```
ipconfig /displaydns | head –n 20
```

## Clear DNS Cache 

```
ipconfig /flushdns
```

## See local DNS resolve settings

```
tail C:\Windows\System32\drivers\etc\hosts
```

## View Windows Routing Table

```
route -4 print
```

## View ARP Table

```
arp -a
```

## View Listening Network Processes

```
netstat -anobp tcp
```

You can also dig further into a specific process from your listing via: `tasklist /v /fi "PID eq XXX" /fo list`