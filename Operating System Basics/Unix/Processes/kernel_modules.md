# Kernel Modules

## Kernel Module Locations:

### Linux:

```
ls -al /lib/modules/$(uname -r)
```

### Solaris:

```
ls -al /kernel
```

### FreeBSD:

```
ls -al /boot/kernel /boot/modules
```

The following command will allow you to show set paths for kernel modules in FreeBSD:

```
kldconfig -r
```

## View Loaded Kernel Modules 

!!!
Loaded Kernel Modules exist within /proc/modules.
!!!

### Linux

```
lsmod 
```

You can also show info about a specific module with: 

```
modinfo
```

### Solaris

```
modinfo 
```

### FreeBSD

```
kldstat [-v]  
```

!!!
Use `-n` to dig into a specific file/module with `kldstat`.
!!!