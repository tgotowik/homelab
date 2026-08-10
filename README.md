# homelab
My homelab setup with opentofu and ansible for my proxmox istance
Some admin documentation for me

## Setup ssh
ssh_askpass
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_homeserver

.bashrc
```
if [ -z "$SSH_AUTH_SOCK" ] ; then
  eval $(ssh-agent -s) > /dev/null
  ssh-add /home/tgotowik/.ssh/id_homeserver 2>/dev/null
fi
```

## DHCP reserved ip
- Create VM
- Make entry in fritz.box

## Add disk from tank volume to vm 
1. Click hard disk on proxmox
2. fdisk /dev/sdb
3. mkfs.ext4 /dev/sdb1
4. lsblk -f
5. add to /etc/fstab

```
UUID=3d5d82da-837f-4314-9082-91007c00dd97       /vaultwarden    ext4    defaults        0       0
```

## Migrate files to vm disk
```
l /dev/zvol/tank/vm-110-disk-0 
apt install kpartx
kpartx -av /dev/zvol/tank/vm-110-disk-0
mkdir -p /mnt/temp_disk
mount /dev/mapper/vm-110-disk-0p1 /mnt/temp_disk/
rsync -aHAXxv --numeric-ids /tank/sync/vaultwarden/ /mnt/temp_disk/
umount /mnt/temp_disk
```
later do kpartx -dv /dev/zvol/tank/vm-110-disk-0 to delete device-mapper
## Resize disk
```
growpart /dev/sdb 1
```