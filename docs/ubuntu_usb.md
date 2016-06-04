## Ubuntu USB Prep
1. Download Ubuntu 14.04.4 Server image from [Ubuntu] (http://www.ubuntu.com/download/server)
2. Create Bootable USB from image. (The easiest way i found was to use the "Startup Disk Creator" from another Ubuntu Machine)
3. Copy the files under ../examples to the usb drive

  ```
  cp ../examples/syslinux/* <usb_drive>:/syslinux
  ```
