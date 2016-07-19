#Con't connect ADB with Linux system#
##code ##

*janny@janny-linux:~/Android$ ls*
*99-vmware-scsi-udev.rules                      android-sdk-linux*
*android-cts-6.0_r7-linux_x86-arm.zip           android-sdk-linux.zip*
*android-cts-verifier-6.0_r7-linux_x86-arm.zip  android-xts-2782496.zip*
*janny@janny-linux:~/Android$ cp 99-vmware-scsi-udev.rules  ./etc/ude/rules.d/*
*cp: 无法创建普通文件'./etc/ude/rules.d/': 没有那个文件或目录*
*janny@janny-linux:~/Android$ sudo cp 99-vmware-scsi-udev.rules ./etc/ude/rules.d/*
*[sudo] janny 的密码： *
*cp: 无法创建普通文件'./etc/ude/rules.d/': 没有那个文件或目录*
*janny@janny-linux:~/Android$ cp 99-vmware-scsi-udev.rules /etc/udev/rules.d/*
*cp: 无法创建普通文件'/etc/udev/rules.d/99-vmware-scsi-udev.rules': 权限不够**
*janny@janny-linux:~/Android$ sudo su*
*root@janny-linux:/home/janny/Android# cp 99-vmware-scsi-udev.rules /etc/udev/rules.d/*
*root@janny-linux:/home/janny/Android# chrom a+r 99-vmware-scsi-udev.rules *
*chrom：未找到命令*
*root@janny-linux:/home/janny/Android# sudo chmod a+r 99-vmware-scsi-udev.rules *
*root@janny-linux:/home/janny/Android# sudo serverice udev restart*
*sudo: serverice：找不到命令*
*root@janny-linux:/home/janny/Android# sudo service udev restart*
*root@janny-linux:/home/janny/Android# *
