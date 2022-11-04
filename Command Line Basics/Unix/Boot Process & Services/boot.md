# Boot Process

!!!
Note: *NIX systems' kernel process is always `/sbin/init`.
!!!

!!!
Note: Boot information is typically stored in `/boot/`
!!!

## *NIX Boot Process

### 1.BIOS/UEFI

At this step, the BIOS/UEFI runs a POST to ensure that hardware and memory functions correctly. Starts the MBR. 

### 2. MBR

Next, the MBR loads and executes the GRUB boot loader.

Typically located at `/dev/hda` or `/dev/sda`.

### 3. GRUB

The Grand Unified Boot Loader (GRUB) intializes the Kernel. 

GRUB Config files is usually located at `/boot/grub/grub.conf`.

### 4. Kernel Initialization

The Kernel executes the Kernel process `/sbin/init`.

### 5. Init 

`/sbin/init` looks at `/etc/inittab` to decide what run level to execute.

Begins execution of run level processes.

Run Levels are:
- 0 – halt
- 1 – Single user mode
- 2 – Multiuser, without NFS
- 3 – Full multiuser mode
- 4 – unused
- 5 – X11
- 6 – reboot

### 6. Runlevel

Run level processes are executed.

Run level folders for scripts to execute:
- Run level 0 – /etc/rc.d/rc0.d/
- Run level 1 – /etc/rc.d/rc1.d/
- Run level 2 – /etc/rc.d/rc2.d/
- Run level 3 – /etc/rc.d/rc3.d/
- Run level 4 – /etc/rc.d/rc4.d/
- Run level 5 – /etc/rc.d/rc5.d/
- Run level 6 – /etc/rc.d/rc6.d/

You can determine your current run level using the command `runlevel`.

Scripts in the run level folders are pre-fixed with a `K` or `S` to tell the system if they should `Kill` or `Start` the script. These scripts are actually symbolic links to scripts in `/etc/init.d/` or `/etc/rc.d/init.d/`. 