N1 OpenWrt.

[![lede](https://img.shields.io/badge/github-lede-blue.svg?style=flat&logo=github)](https://github.com/coolsnowwolf/lede)
![GitHub](https://img.shields.io/github/license/mingxiaoyu/N1Openwrt)



默认自定义防火墙: iptables -t nat -I POSTROUTING -o eth0 -j MASQUERADE



# 如何使用
1. fork项目
2. 在secrets中创建RELEASES_TOKEN，一般一次编译要2~4小时，所以要创建一个github发布用的token。
3. 点击Actions -> Workflows -> Run workflow -> Run workflow 
4. N1 Multiple Version 多版本编译
5. N1 Single Version 只编译一个版本
6. Update Checker, 上游更新则编译。MULTIPLE_BUILD: true **编译mini和plus多版本编译**  false，**只编译mini**

------

## 用户名和密码
 * User: root
 * Password: password
 * Default IP: 192.168.66.1
------

## app list:（mini 图不代表最新的）
 * UU网游加速器
 * jd-dailybonus
 * ssr+
 * ServerChan
 * unblockmusic
 * aria2
 * ddns
 * samba4
 * KMS 
 * frp
 * docker
 * cifs(挂载 SMB/CIFS 网络共享文件夹)
 * vsftpd
 * usb_printer
 * zerotier
 * flowoffload
 * WIFI
 
 ![applist](https://github.com/mingxiaoyu/N1Openwrt/blob/master/imgs/mini.jpg?raw=true)
 
 ------
 # N1 U盘写入刷emmc
```
cd      /root
./install-to-emmc.sh
```
如果一直卡在fdisk失败那里的解决办法：一是再多试几次，如果还不成功，则需要手动清空分区表然后再重试，具体命令:
```
  dd   if=/dev/zero   of=/dev/mmcblk2  bs=512  count=1  &&  sync
```

升级降级方法统一为：
把 update-amlogic-openwrt.sh 及 img镜像上传至  /mnt/mmcblk2p4
```
cd    /mnt/mmcblk2p4
chmod   755  update-amlogic-openwrt.sh
./update-amlogic-openwrt.sh    xxxxx.img
```
------
 # 感激 
 [P3TERX](https://github.com/P3TERX/Actions-OpenWrt)提供的脚本参考
 
 ## 云编译的规格
https://docs.github.com/en/actions/reference/virtual-environments-for-github-hosted-runners#supported-runners-and-hardware-resources

