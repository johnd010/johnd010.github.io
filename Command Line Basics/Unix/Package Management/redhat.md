# Package Management in RedHat (RedHat, CentOS, Fedora, SUSE)

## rpm

### List Installed Packages

```
rpm -qa
```

### List Most Recently Installed Packages

```
rpm -qa --last | head
```

### Query a Specific Package

```
rpm -qi <package_name>
```

### ID Package where Binary is included

```
rpm -qf </bin/ls>
```

### List Files in a Package

```
rpm -ql <pkgname>
```

## yum / dnf

View yum configuration files via:

```
cat /etc/yum.conf
```

You can view repos on the system by checking the following directory:

```
ls /etc/yum.repos.d/
```

!!!
***NOTE:*** View the `BASEURL` field in the repo files. This tells you where the repo is pulling from, to include local repos. 
!!!