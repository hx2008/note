```
# mdadm -Cv  /dev/md0  -l5  --raid-devices=4  /dev/sdb /dev/sdc /dev/sdd /dev/sde
# mkfs.ext4 /dev/md0
# parted /dev/md0
```
