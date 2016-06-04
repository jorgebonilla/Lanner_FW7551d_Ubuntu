# Ubuntu on Lanner FW-7551d
###Description:
This project describes the installation of Ubuntu 14.04.4 Server on a Lanner FW-7551d

###Prerequisites:

- [Lanner FW-7551d](http://www.lannerinc.com/products/x86-network-appliances/desktop/fw-7551)
- Basic knowledge of Ubuntu  
- Serial Connection: Make sure to check out the [Serial Configuration Page](./serial.md)
- Prep the [Ubuntu bootable USB](./ubuntu_usb.md)

##Ubuntu 14.04.4 installation
1.- Boot from Ubuntu USB drive. If this is the first time please run the disk and memory check. After that select **Install via Console**.

```
┌───────────────────────────────┐
│     Installer boot menu       │
├───────────────────────────────┤
│ Install via Console           │
│ Check disc for defects        │
│ Test memory                   │
│ Boot from first hard disk     │
│ Advanced options            > │
│ Help                          │
└───────────────────────────────┘      
```

2.- You'll get this error message,   Select "No" and then "Continue" in the next screen

```
┌───────────────────┤ [!!] Detect and mount CD-ROM ├────────────────────┐
│                                                                       │
│ Your installation CD-ROM couldn't be mounted. This probably means     │
│ that the CD-ROM was not in the drive. If so you can insert it and try │
│ again.                                                                │
│                                                                       │
│ Retry mounting the CD-ROM?                                            │
│                                                                       │
│     <Yes>                                                    <No>     │
│                                                                       │
└───────────────────────────────────────────────────────────────────────┘        

┌─────────────────┤ [!!] Detect and mount CD-ROM ├──────────────────┐
│                                                                   │
│                     Installation step failed                      │
│ An installation step failed. You can try to run the failing item  │
│ again from the menu, or skip it and choose something else. The    │
│ failing step is: Detect and mount CD-ROM                          │
│                                                                   │
│                            <Continue>                             │
│                                                                   │
└───────────────────────────────────────────────────────────────────┘  
```

3.- Select "Execute a shell"

```
┌─────────┤ [?] Ubuntu installer main menu ├─────────┐
│                                                    │
│ Choose the next step in the install process:       │
│                                                    │
│       Choose language                              │
│       Configure the keyboard                       │
│       Detect and mount CD-ROM                      │
│       Load debconf preconfiguration file           │
│       Load installer components from CD            │
│       Change debconf priority                      │
│       Check the CD-ROM(s) integrity                │
│       Save debug logs                              │
│       Execute a shell                              │
│       Abort the installation                       │
│                                                    │
└────────────────────────────────────────────────────┘  
```

4.- Select "Continue", This will take you to a linux command prompt.

```
┌────────────────────────┤ [!] Execute a shell ├────────────────────────┐
│                                                                       │
│                           Interactive shell                           │
│ After this message, you will be running "ash", a Bourne-shell clone.  │
│                                                                       │
│ The root file system is a RAM disk. The hard disk file systems are    │
│ mounted on "/target". The editor available to you is nano. It's very  │
│ small and easy to figure out. To get an idea of what Unix utilities   │
│ are available to you, use the "help" command.                         │
│                                                                       │
│ Use the "exit" command to return to the installation menu.            │
│                                                                       │
│     <Go Back>                                          <Continue>     │
│                                                                       │
└───────────────────────────────────────────────────────────────────────┘   
```

5.- Determine in which device is the USB currently mounted:

```
~ # mount
[...]
/dev/sdb1 on /media type vfat [...]  
```

In this example it is **/dev/sdb1**, mount that same device on /cdrom

```
mount -t vfat /dev/sdb1 /cdrom
```
Verify:

```
~ # mount
[...]
/dev/sdb1 on /media type vfat [...]
/dev/sdb1 on /cdrom type vfat [...]
```

Go back to installer:

```
exit  
```

From this point forward the installation is the usual Ubuntu install. Check this [link](./ubuntu_install_steps.md) for step by step instructions
