# Solaris

## Service Management Facility (SMF)

SMF was added in Solaris 10.

Services are defined by manifest XML files located in `/var/svc/manifest/`

!!!
***Example:*** `/var/svc/manifest/network/ssh.xml`
!!!

SMF relies on a database that is located at `/etc/svc/repository.db`.

### Show Status of Services

```
svcs [-a]
```

### Display Information about a Specific Service

```
svcs -l <servicename>
```

### List Processes Associated with a Specific Service

```
svcs -p <servicename>
```

### Enable and Start a Service

```
svcadm enable svc:/network/http:apache2
```

### View Detailed Status Information about a Specific Service

```
svcs -xv <servicename>
```

## SysV Init

Not used much anymore. Used on older Solaris systems as well as other miscellaneous Unix systems like AT&T Unix.

The first thing run by SysV Init is the script located at `/etc/rc.d/rc.sysinit`.

Run level service scripts located at `/etc/rc.d/rcX.d/` where `X` is the run level.

### Manage/List init services

```
chkconfig
```