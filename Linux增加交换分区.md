# Linux增加交换分区
### 查看交换分区大小
`free -h`
### 删除交换分区
`swapoff -a`
### 新增交换分区
* 创建swap分区文件
* `dd if=/dev/zero of=/usr/swap/swapfile bs=1M count=2048`
* bs是每块的大小(不超过`free -h`中buff/cache的值)，count是块的数量，bs*count，为swap文件大小，1M*2048=2G。
* 格式化交换分区文件
* mkswap /usr/swap/swapfile
### 添加开机启动
* vim /etc/fstab
* 注释 /swap none swap sw 0 0
* 新增 /usr/swap/swapfile swap swap defaults 0 0
### END
