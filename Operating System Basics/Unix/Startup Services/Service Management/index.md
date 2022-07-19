## Determine Service Manager

You can determine the service manager that is in use by the system by running the following commands:

### rpm

You can determine which service manager is in use on systems using rpm (such as CentOS, Red Hat, etc.) via the following command:

```
rpm -qf /sbin/init
```


### dpkg / systemd

You can identify that systemd is in use by running the following:

```
ls -la /sbin/init 
```

You will see that `/sbin/init` should have a symbolic link to `/lib/systemd/systemd`.

Additionally, you can run the command listed below and it should tell you that the `/sbin/init` in use is using systemd.

```
dpkg -S /sbin/init
```