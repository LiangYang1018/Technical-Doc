``` she
[root@guangbao-10-190-90-201 test]# mc ls local
[2022-05-10 16:21:37 CST]     0B ai-server/
[2022-05-15 12:21:23 CST]     0B demo/
[2022-05-20 11:42:49 CST]     0B nest-582413053216504832/
[2022-05-09 11:25:10 CST]     0B nest-ks/
[2022-04-28 20:43:57 CST]     0B test/
[2022-05-12 16:04:09 CST]     0B vmimage/
[root@guangbao-10-190-90-201 test]# mc ls test
[root@guangbao-10-190-90-201 test]# mc ls local/test
[2022-05-12 19:33:57 CST]   185B STANDARD test.yaml
[2022-05-20 14:28:07 CST]     0B image/
[root@guangbao-10-190-90-201 test]# mc ls local/demo
[2022-05-20 14:28:33 CST]     0B myimage/
[2022-05-20 14:28:33 CST]     0B test/
[root@guangbao-10-190-90-201 test]# mc ls local/demo/test
[2022-05-18 15:31:11 CST] 3.0GiB STANDARD cn_windows_7_enterprise_x64_dvd_x15-70741.iso
```

``` shell
mc rm local/demo/test/CentOS_7_64.qcow2
```

