# FreeBSD

FreeBSD uses rc scripts for startup services.

The configuration files for rc are located at `/etc/defaults/rc.conf` and `/etc/rc.conf`.

## Service Command

The `service` command is used to control and manage rc services in FreeBSD.

The `service` command pulls information from `/etc/rc.d/` and `/usr/local/etc/rc.d/`.

### Show Started Services

```
service -e
```

### Show Installed Services

```
service -l
```

### Look at Service Scripts for Dependencies/Other Info

```
less /etc/rc.d/ftpd
```

### Start a Service

```
service ftpd start
service ftpd onestart
```

### Check Status of a Service

```
service ftpd status
service ftpd onestatus
```

### Stop a Service

```
service ftpd stop
```