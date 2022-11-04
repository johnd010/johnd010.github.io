# Package Management in Solaris

## pkg tools

### Display installed packages

```
pkginfo
```

### View Information about a Package

```
pkgchk -l <pkg>
```

### ID Package where Binary is included

```
pkgchk -l -p </usr/bin/ls>
```

### Check the Status of a pkg

```
pkgchk -v <pkgname>
```

### Repositories that packages reference (Solaris 10 and lower)

```
head /var/sadm/install/contents
```

### Install a new Package

```
pkgadd <pkg>
```

### Remove a Package

```
pkgrm <pkgname>
```

### Show the Package Source/Publisher

```
pkg publisher <pkgname>
```

