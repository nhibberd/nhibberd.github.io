# Install
###### Locale

``` 
/etc/locale.gen
locale-gen
export LANG=en_AU.UTF-8
```

### [Partitioning](./linux/partioning.md)
###### BIOS/UEFI

###### Mount
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

### Pacman Mirror
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

### Base System
`pacstrap -i /mnt base base-devel`




# Maintenance

## Network
### Wired

### Wireless
