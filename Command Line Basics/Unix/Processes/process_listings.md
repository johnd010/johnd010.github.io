# Process Listings

Process listings can be listed using the following commands across nix variants:

```
ps
```

```
ss
```

!!!
***Note:*** Kernel threads have PPID 2 in Linux and PPID 0 on FreeBSD/Solaris.
!!!

## Linux / Solaris

For most Linux variants and Solaris, my goto syntax is:

```
ps -elf
```

Additionally, you can show GUI tree listing with `-H`.

Specify specific columns with `-o` option.

## FreeBSD  

For FreeBSD, my goto syntax is:

```
ps -aux
```

Specify specific columns with `-o` option.
