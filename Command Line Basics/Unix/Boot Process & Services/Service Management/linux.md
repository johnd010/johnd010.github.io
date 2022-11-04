---
label: Linux
---

# Linux (CentOS, Debian, etc.)

## Upstart

In Upstart, run levels are defined in `/etc/init/rc-sysinit.conf`.

Upstart uses "Jobs", which are defined in `/etc/init/`. These jobs fall into three categories:
- Task Jobs - Task Jobs define a process that has a definite end time.
- Service Jobs - Service Jobs define a process which is designed to be long-running with no defined end time.
- Abstract Jobs - Abstract Jobs spawn no child process, but they can be manually started or stopped. These are primarily used within upstart itself.

Upstart event information is described further in the upstart manual `man upstart-events`.

Upstart can easily define service configurations in the following types of files: `/etc/init/<service>.conf`. 

!!!
***UFW Service Example:*** 
```
start on (starting network-interface
or starting network manager
or starting network)
```
!!!

### Interact with Upstart Services

```
initctl
```

### List Upstart Jobs

```
initctl list
```

### List Running Upstart Jobs

```
initctl list | grep running
```

### Query Individual Service Status'

```
initctl status <service>
```

### Start Service

```
initctl start <service>
```

## Stop Service

```
initctl stop <service>
```

## Systemd

Systemd makes use of unit files. 

Uses default target to determine which units are started at startup.

### Get the default target for the system:

```
systemctl get-default
```

### View cgroup hierarchy

```
systemd-cgls
```

### View cgroup in process list

```
ps -eo comm, cgroup
```

### View resource Utilization by cgroups

```
systemd-cgtop
```

### Analyze length of time to start service units

```
systemd-analyze critical-chain
```

### Troubleshoot units by seeing length of time to start

```
systemd-analyze blame
```

### List service units with systemctl

```
systemctl list-units --type service
```

### List Startup Services

```
systemctl list-unit-files | grep enabled
```

### View Status of a Service

```
systemctl status <service_name> [-l]
```

### View the Unit File for a Service

```
systemctl cat <service_name.service>
```

### Start a Service

```
systemctl start <service_name>
```

### Stop a Service

```
systemctl stop <service_name>
```

### View Service Dependencies

```
systemctl list-dependencies --before <service_name.service>
```

### List Required and Wanted Units (green=active, red=inactive)

```
systemctl list-dependencies multi-user.target
```

### Disable Service Start at Boot

```
systemctl disable <service_name.service>
```

### Make it so a Service can't be started

The `mask` command makes it so that you can no longer start the service via the CLI. 

```
systemctl mask <service_name.service>
```

!!!
`rc-local.service` starts `/etc/rc.d/rc.local`... You need to ensure `/etc/rc.local` has execute permissions.
!!!