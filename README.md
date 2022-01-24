MNT Reform FreeBSD Enablement Project
=====================================

This is a project to port FreeBSD to the MNT Reform laptop.

This repository contains scripts useful to the development process.

To build, 
  - `git clone git://git.freebsd.org/src.git src`
  - `mkdir -p obj nfsroot/tree` (nfsroot may be on NFS if you wish)
  - Place `imx8mq-mnt-reform2.dtb` and `flash.bin` (MNT Reform U-Boot) in `nfsroot/`.
  - `./do_buildworld`
  - `./do_buildkernel`
  - To create a FreeBSD tree under `nfsroot/tree`, run:
    - `./do_installworld`
    - `./do_installdistribution`
    - `./do_installkernel`
  - To create an image which can be flashed to an SD card, including U-boot, run `./mkimg`.
    This will create an image at `nfsroot/target.img`. If the image already exists,
    it will only have a limited number of files updated (currently the bootloader),
    so delete the file before running `./mkimg` if you want userspace updated.

