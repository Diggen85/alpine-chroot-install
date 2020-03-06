# Install Raspbian Linux in chroot 
## About

This `raspbian-chroot-install` script simplifies installation of [Raspbian](https://www.raspbian.org/) in chroot.
It utilizes _qemu-user_ and _binfmt_ to emulate armhf.

The main purpose of this script is to easily create an environment for (my) [c't Raspion](https://github.com/ct-Open-Source/ctraspion) development.
It is a fork of [Alpine-chroot-install](https://github.com/alpinelinux/alpine-chroot-install) but has taken much more rework than I initially thought.

The Script works for me, in my netinst Debian VM. I can not guarantee that it will work anywhere else but it should run on an actual Debian or Ubuntu. You are free to open an Issue on Github.


## Requirements

* Linux system with common userland (Busybox or GNU coreutils) 
* POSIX-sh compatible shell (e.g. Busybox ash, dash, Bash, ZSH)
* qemu-user ≥ 2.6 and binfmt, or apt-get (I don't know if 2.6 is really needed. This requirement is based on alpine-chroot-install)
* loopback device / losetup to mount the raspbian.img
* Filesystem-support for ext4 because this is the actual used FS in Raspbian
* unzip for unziping the Image and parted for resizing

## Usage
* `raspbian-chroot-install -h` - for help
* `sudo raspbian-chroot-install` - downloads raspbian-latest, adds 4GB Space to the Image, installs qemu and binmft (under Debian/Ubunu) and setups the chroot-environment under /raspbian
*	`/raspbian/raspbian-chroot enter -u pi /bin/bash` - enters the chroot with BASH-Shell as User pi (UID:1000, raspbians default User)


## License

This project is licensed under [MIT License](http://opensource.org/licenses/MIT/).
For the full text of the license, see the LICENSE file.
