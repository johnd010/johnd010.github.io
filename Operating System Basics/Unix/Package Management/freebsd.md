# Package Management in FreeBSD

## Check Package Repositories on System

```
cat /etc/pkg/FreeBSD.conf
```

## pkg_info

### Show files for package

```
pkg_info -L <pkg_name>
```

### ID Package where Binary is included

```
pkg_info -W </usr/local/bin/ls>
```

## pkgng

### Show installed packages

```
pkg info
```

### Obtain Information about a Specific Package

```
pkg info <pkg name>
```

### List Files in a Package

```
pkg list <pkg name>
```

### ID Package where Binary is included

```
pkg which /usr/local/bin/binary1
```