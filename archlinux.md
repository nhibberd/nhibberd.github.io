# Install
##### locale

``` 
/etc/locale.gen
locale-gen
export LANG=en_AU.UTF-8
```

### [Partitioning](./linux/partioning.md)
##### BIOS/UEFI

##### munt
```
lsblk -f

mount /dev/sda1 /mnt
mkdir /mnt/home
mount /dev/sda2 /mnt/home
```

_Optional_
```
mkdir /mnt/boot
mount /dev/sdXY /mnt/boot
```

##### pacman mirror
` /etc/pacman.d/mirrorlist `
```
## Australia
Server = http://mirror.internode.on.net/pub/archlinux/$repo/os/$arch
Server = http://mirror.aarnet.edu.au/pub/archlinux/$repo/os/$arch
Server = http://ftp.iinet.net.au/pub/archlinux/$repo/os/$arch
Server = http://mirror.optus.net/archlinux/$repo/os/$arch
Server = http://syd.mirror.rackspace.com/archlinux/$repo/os/$arch
Server = http://ftp.swin.edu.au/archlinux/$repo/os/$arch
Server = http://archlinux.mirror.uber.com.au/$repo/os/$arch
```

##### base System
`pacstrap -i /mnt base base-devel`

##### fstab
`genfstab -U -p /mnt >> /mnt/etc/fstab`

To use labels in place of uuid's replace `-U` with `-L`

##### chroot and configure
`arch-chroot /mnt /bin/bash`
###### locale
``` 
/etc/locale.gen
locale-gen
echo LANG=en_AU.UTF-8 > /etc/locale.conf
export LANG=en_AU.UTF-8
```
###### time
`ln -s /usr/share/zoneinfo/Australia/Brisbane /etc/localtime`
`hwclock --systohc --utc`

##### hostname
`echo _ > /etc/hostname`
Add entry to `/etc/hosts`

##### network
`systmectl enable dhcpcd.service`
See 
# Maintenance

## Network
### Wired

### Wireless
