### diskutil list<br>
此时会得到U盘的设备名字，【/dev/disk2】通过这个U盘存储容量可以知道。<br>
### diskutil unmountDisk /dev/disk2<br>
接着输入卸载U盘命令：【diskutil unmountDisk /dev/disk2】，看到图二的提示说明卸载成功了的。<br>
### sudo dd if=system.iso of=/dev/disk2 bs=1m<br>
system.iso为所要制作系统盘iso, /dev/disk2 为U盘名字 bs=1m是刻录的速度<br>
