命令行安装deb程序

 ```sh
dpkg -i xxx.deb
 ```

apt-cache search openssl
 apt list --installed|grep openssl


并杀死进程
 kill -s 9 `pgrep firefox`
 or
 killall -9 firefox


 查看流量
 sar -n DEV 1 2
命令后面1 2 意思是：每一秒钟取1次值，取2次。
DEV显示网络接口信息
另外，-n参数很有用，他有6个不同的开关：DEV | EDEV | NFS | NFSD | SOCK | ALL ，其代表的含义如下：
DEV显示网络接口信息。
EDEV显示关于网络错误的统计数据。
NFS统计活动的NFS客户端的信息。
NFSD统计NFS服务器的信息
SOCK显示套接字信息
ALL显示所有5个开关

Linux下如何查看版本信息
 ```sh
uname －a #（Linux查看版本当前操作系统内核信息）

lsb_release -a
cat /etc/issue  或cat /etc/redhat-release #（Linux查看版本当前操作系统发行版信息）

cat /proc/cpuinfo #（Linux查看cpu相关信息，包括型号、主频、内核信息等）

 ```