~~~shell
[root@master ~]# lsblk
NAME            MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda               8:0    0   50G  0 disk
├─sda1            8:1    0    1G  0 part /boot
└─sda2            8:2    0   49G  0 part
  ├─centos-root 253:0    0   47G  0 lvm  /
  └─centos-swap 253:1    0    2G  0 lvm
sr0              11:0    1  4.4G  0 rom


[root@master ~]# lsblk
NAME            MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda               8:0    0   50G  0 disk
├─sda1            8:1    0    1G  0 part /boot
└─sda2            8:2    0   49G  0 part
  ├─centos-root 253:0    0   47G  0 lvm  /
  └─centos-swap 253:1    0    2G  0 lvm
sdb               8:16   0   10G  0 disk
sr0              11:0    1  4.4G  0 rom

~~~



~~~shell
[nest@ECF-NM-HHHT-edge-32 ~]$ sudo blkid
/dev/sdm1: UUID="977fca36-7133-4139-ac8c-256646cb42e0" TYPE="xfs" 
/dev/sdm2: UUID="7d321f93-0bd5-4c5e-bcc9-37edf98cdbfb" TYPE="xfs" 
/dev/sdm3: UUID="0EAD-D197" TYPE="vfat" 
/dev/sdm5: UUID="39d8e00a-21a0-4b01-93e2-99917bed3e92" TYPE="xfs" 
/dev/sda1: UUID="5a9c48a1-9c23-4413-a6d6-fbf17c67fbb1" TYPE="xfs" PARTUUID="f5ecc897-3de9-4175-8b71-394999e62d07" 
/dev/sdb1: UUID="a7070c44-b16c-4753-9485-02c09e8015da" TYPE="xfs" PARTUUID="d9a856e3-d7fa-4077-8d65-d16211510b16" 
/dev/sde1: UUID="00b42512-5bf1-4f46-8db9-7f9d1d5e5fb9" TYPE="xfs" PARTUUID="edd74a01-8aed-45bb-95f9-497db37db45c" 
/dev/sdc1: UUID="3b653f08-fb45-44f6-84ef-dceba920f639" TYPE="xfs" PARTUUID="b4c02d80-58da-45cf-8b1a-19d543ace6b1" 
/dev/sdd1: UUID="732d3a7b-49d1-4c81-9a56-60309069af0e" TYPE="xfs" PARTUUID="f6ef1c14-ec39-42cb-a417-c9741ef51fa2" 
/dev/sdk1: UUID="485298d9-d6d1-4174-8f18-aef0271f8e1a" TYPE="xfs" PARTUUID="dcc3d89c-d4bd-4eeb-ae32-d888f8c5ba56" 
/dev/sdl1: UUID="a527b01c-fc09-4b14-a56f-3095786a7a9b" TYPE="xfs" PARTUUID="4141f323-5fd8-47f7-8d7e-81a1435ccd72" 
/dev/sdj1: UUID="50c37446-c89a-4cb1-88b8-50c31ea6af96" TYPE="xfs" PARTUUID="feb2002a-0766-4e94-a1d3-06a6bbe4305f" 
/dev/sdf1: UUID="3454c704-6820-4565-8e42-68ee904b60a8" TYPE="xfs" PARTUUID="6c14078d-a954-477b-b5c0-54f153564412" 
/dev/sdi1: UUID="67718623-68d8-438d-ac20-e44f826ca215" TYPE="xfs" PARTUUID="5faa4c61-216f-4850-bb20-496ab2248abc" 
/dev/sdh1: UUID="689eee8d-7cb5-452c-87e1-ec9da67f13c3" TYPE="xfs" PARTUUID="b8a703f8-f8e6-4072-a714-7a71bd3fe653" 
/dev/sdg1: UUID="9e219a8d-d31b-40ea-9bc4-7220d3d0c89d" TYPE="xfs" PARTUUID="756d5b86-b474-4a64-bdc7-12775177b0fc"
~~~





~~~shell
sudo fdisk /dev/sdc
sudo mkfs -t xfs /dev/sda1
sudo mkdir /data5
sudo mount /dev/sdc1 /data3

vim /etc/fstab
UUID= /data1                  xfs     defaults        0 0
~~~

~~~ shell
/dev/sdb1: UUID="cc6f3544-21ab-4c4b-bddc-9bce5671bed7" TYPE="xfs"
/dev/sdc1: UUID="9cdb3088-c174-4fb5-9c2a-3d275d60e7c8" TYPE="xfs"

~~~







