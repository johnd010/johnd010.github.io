# Package Management in Debian

## dpkg

### List Installed Packages

```
dpkg -l
```

### Query a Specific Package

```
dpkg-query
```

### Display Status of a Package

```
dpkg -s <package/file>
```

### List Files Inside a Package

```
dpkg --listfiles <pkgname>
```

### ID Package where Binary is included

```
dpkg -S <binary path>
```

### Verify Integrity of a Package

```
dpkg --verify <pkg>
```

## apt

You can view sources for dpkg/apt via:

```
cat /etc/apt/sources.list
cat /etc/apt/sources.list.d
```