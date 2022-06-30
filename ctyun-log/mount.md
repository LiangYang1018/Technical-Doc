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
/dev/sdb1: UUID="abe0df3e-73de-4b74-83b2-70efe4375cd9" TYPE="xfs" PARTUUID="d7153b74-86ae-4b9c-b491-0a93d82ca629"
/dev/sda1: UUID="123ec837-dd56-430c-8f2d-890e9fe662df" TYPE="xfs"
/dev/sda2: UUID="q6tNPo-8xsz-kxSh-Eabs-VF13-BStl-qsCE0Y" TYPE="LVM2_member"
/dev/sr0: UUID="2020-11-04-11-36-43-00" LABEL="CentOS 7 x86_64" TYPE="iso9660" PTTYPE="dos"
/dev/mapper/centos-root: UUID="929b54f7-86b6-4df0-80ff-5ab98602725b" TYPE="xfs"
/dev/mapper/centos-swap: UUID="1ab4d377-d22f-4302-8541-06bc9aa234f9" TYPE="swap"

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
UUID=5a9c48a1-9c23-4413-a6d6-fbf17c67fbb1 /data1                  xfs     defaults        0 0
UUID=a7070c44-b16c-4753-9485-02c09e8015da /data2                  xfs     defaults        0 0
UUID=3b653f08-fb45-44f6-84ef-dceba920f639 /data3                  xfs     defaults        0 0
UUID=732d3a7b-49d1-4c81-9a56-60309069af0e /data4                  xfs     defaults        0 0
UUID=00b42512-5bf1-4f46-8db9-7f9d1d5e5fb9 /data5                  xfs     defaults        0 0
UUID=3454c704-6820-4565-8e42-68ee904b60a8 /data6                  xfs     defaults        0 0
UUID=9e219a8d-d31b-40ea-9bc4-7220d3d0c89d /data7                  xfs     defaults        0 0
UUID=689eee8d-7cb5-452c-87e1-ec9da67f13c3 /data8                  xfs     defaults        0 0
UUID=67718623-68d8-438d-ac20-e44f826ca215 /data9                  xfs     defaults        0 0
UUID=50c37446-c89a-4cb1-88b8-50c31ea6af96 /data10                  xfs     defaults        0 0
UUID=485298d9-d6d1-4174-8f18-aef0271f8e1a /data11                  xfs     defaults        0 0
UUID=a527b01c-fc09-4b14-a56f-3095786a7a9b /data12                  xfs     defaults        0 0
~~~



~~~shell
sudo fdisk /dev/sdc
sudo mkfs -t xfs /dev/sda1
sudo mkdir /data5
sudo mount /dev/sdc1 /data3

UUID= /data1                  xfs     defaults        0 0
~~~





~~~shell
UUID=6b657a77-a4ed-4691-b5c2-9cade60aab09 /data1                  xfs     defaults        0 0
UUID=2f19968f-710a-4565-a376-ce734337107d /data2                  xfs     defaults        0 0
UUID=e726591d-fb71-4b18-b71d-5d17089288a0 /data3                  xfs     defaults        0 0
UUID=fdd76955-9bf3-4fd0-98fe-8fac855707a2 /data4                  xfs     defaults        0 0
UUID=643b9c61-b56b-40dd-84e3-2c22d62573ec /data5                  xfs     defaults        0 0
UUID=3f9341c1-d5e3-4f2f-b98c-f926cb5ec045 /data6                  xfs     defaults        0 0
UUID=047cf788-ebad-4d30-a8df-e7ffaafd8228 /data7                  xfs     defaults        0 0
UUID=9e2be84a-2e2b-4bce-9020-1bdce805a949 /data8                  xfs     defaults        0 0
UUID=c14ff543-3b3a-4082-aa77-cfbe61a87683 /data9                  xfs     defaults        0 0
UUID=d1f6cb4c-94d3-4dcc-9bba-dd90407fa824 /data10                  xfs     defaults        0 0
UUID=e0c147de-7ccf-443b-8ca2-b6bfd0470300 /data11                  xfs     defaults        0 0
UUID=b052da89-75ca-42fe-8566-1cf736640bf8 /data12                  xfs     defaults        0 0
~~~



~~~she
UUID=a6e06ec1-3d25-49af-b1e1-d9c51e8d1aa2 /data1                  xfs     defaults        0 0
UUID=6eeed465-6b09-41cd-89ff-c3dbda4e255f /data2                  xfs     defaults        0 0
UUID=be3631ec-ea7f-43b0-bfe4-924191a0d2c7 /data3                  xfs     defaults        0 0
UUID=7a0562c6-9493-470e-b863-998afd65b885 /data4                  xfs     defaults        0 0
UUID=3209c4e9-97b0-4efd-9079-4a7d553bc315 /data5                  xfs     defaults        0 0
UUID=e6aae867-395e-4ab3-95f1-60b503d7f51e /data6                  xfs     defaults        0 0
UUID=9712fe80-ec95-47da-a666-9525c5fca440 /data7                  xfs     defaults        0 0
UUID=03c12497-bd6e-484b-a2ed-f3ef0fc6d39a /data8                  xfs     defaults        0 0
UUID=280b9533-a1dc-48c5-93e9-35e12dded755 /data9                  xfs     defaults        0 0
UUID=708d3957-aaa5-49f6-9c36-7db547d70d11 /data10                  xfs     defaults        0 0
UUID=c71189ea-8064-4a23-8189-fab4499582af /data11                  xfs     defaults        0 0
UUID=1083d1b6-f49e-4b7c-ab30-0888ba6fdb29 /data12                  xfs     defaults        0 0
~~~

