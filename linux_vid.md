#Linux系统无法连接ADB，由于设备VID未添加#
##命令行如下： ##
####拷贝文件至./etc/ude/rules.d/目录####

    janny@janny-linux:~/Android$ sudo su
    root@janny-linux:/home/janny/Android# cp 99-vmware-scsi-udev.rules /etc/udev/rules.d/
    
####添加权限####
    
    root@janny-linux:/home/janny/Android# sudo chmod a+r 99-vmware-scsi-udev.rules 

####重启服务####

    root@janny-linux:/home/janny/Android# sudo service udev restart





##99-vmware-scsi-udev.rules   Code##
               # VMware SCSI devices Timeout adjustment
               #
               # Modify the timeout value for VMware SCSI devices so that
               # in the event of a failover, we don't time out.
               # See Bug 271286 for more information.

               ACTION=="add", SUBSYSTEMS=="scsi", ATTRS{vendor}=="VMware, ", ATTRS{model}=="VMware Virtual S", RUN+="/bin/sh -c 'echo 180 >/sys$DEVPATH/timeout'"

               SUBSYSTEM=="usb", ATTRS{idVendor}=="1782",ATTRS{idProduct}=="5d24", MODE="0666"
