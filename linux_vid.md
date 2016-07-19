#Con't connect ADB with Linux system#
##command in linux ##

    janny@janny-linux:~/Android$ cp 99-vmware-scsi-udev.rules  ./etc/ude/rules.d/
    cp: 无法创建普通文件'./etc/ude/rules.d/': 没有那个文件或目录
    janny@janny-linux:~/Android$ sudo cp 99-vmware-scsi-udev.rules ./etc/ude/rules.d/
    [sudo] janny 的密码： 
    cp: 无法创建普通文件'./etc/ude/rules.d/': 没有那个文件或目录
    janny@janny-linux:~/Android$ cp 99-vmware-scsi-udev.rules /etc/udev/rules.d/
    cp: 无法创建普通文件'/etc/udev/rules.d/99-vmware-scsi-udev.rules': 权限不够
    janny@janny-linux:~/Android$ sudo su
    root@janny-linux:/home/janny/Android# cp 99-vmware-scsi-udev.rules /etc/udev/rules.d/
    root@janny-linux:/home/janny/Android# chrom a+r 99-vmware-scsi-udev.rules 
    chrom：未找到命令
    root@janny-linux:/home/janny/Android# sudo chmod a+r 99-vmware-scsi-udev.rules 
    root@janny-linux:/home/janny/Android# sudo serverice udev restart
    sudo: serverice：找不到命令
    root@janny-linux:/home/janny/Android# sudo service udev restart





##99-vmware-scsi-udev.rules   Code##
               # VMware SCSI devices Timeout adjustment
               #
               # Modify the timeout value for VMware SCSI devices so that
               # in the event of a failover, we don't time out.
               # See Bug 271286 for more information.

               ACTION=="add", SUBSYSTEMS=="scsi", ATTRS{vendor}=="VMware, ", ATTRS{model}=="VMware Virtual S", RUN+="/bin/sh -c 'echo 180 >/sys$DEVPATH/timeout'"

               SUBSYSTEM=="usb", ATTRS{idVendor}=="1782",ATTRS{idProduct}=="5d24", MODE="0666"
