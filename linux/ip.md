

引用： https://www.linuxidc.com/Linux/2015-08/121983.htm

ip a

这条命令将会列出所有网络接口的相关信息。

你说你只想看 IPv4 相关信息，那么可以这样。

ip -4 a

你又说你想看特定的网络接口的相关信息，那么用如下命令查看无线网卡连接信息。

ip a show wlan0

你甚至可以定位更具体的信息，欲查看 wlan0 上的 IPv4 信息，那么可以这样。

ip -4 a show wlan0

还可以这样列出正在运行的网络接口。

ip link ls up

修改配置网络接口

接下来让我们来学习 ip 命令的核心功能——修改配置网络接口。假如你想为第一个以太网的网卡（ eth0 ）安排一个特定的地址。用 ifconfig 的话，看起来是这样的。

ifconfig eth0 192.168.1.101

那么用 ip 命令却是这样的。

ip a add 192.168.1.101/255.255.255.0 dev eth0

简短一点可以这样。

ip a add 192.168.1.101/24 dev eth0

显然这样的话，你需要知道你要安排的地址的子网掩码。

同样的方式，你可以这样删除一个网卡的地址。

ip a del 192.168.1.101/24 dev eth0

如果你想简单的清除所有接口上的所有地址，只需要这样即可。

ip -s -s a f to 192.168.1.0/24

ip 命令另一方面还能激活/禁用网络接口。

禁用 eth0

ip link set dev eth0 down

激活 eth0

ip link set dev eth0 up

使用 ip 命令，我们还可以添加/删除默认的网关，就像这样。

ip route add default via 192.168.1.254

如果你想获得网络接口的更多细节，你可以编辑传输队列，给速度慢的接口设置一个低值，给速度快的设置一个较高值。那么你需要像这样做。

ip link set txqueuelen 10000 dev eth0

该命令设置了一个很长的传输队列。你应该设置一个最适合你硬件的值。

还可以用 ip 命令为网络接口设置最大传输单元。

ip link set mtu 9000 dev eth0

一旦你做了改变，便可以使用 ip a list eth0 来检验是否生效。

管理路由表

其实还可以使用 ip 命令来管理系统路由表。这是 ip 命令非常有用的一个功能。并且你应该小心使用。

查看所有路由表。

ip r

现在你想要路由的所有流量从 eth0 网卡的192.168.1.254网关通过，那么请这样做。

ip route add 192.168.1.0/24 dev eth0

删除这个路由。

ip route del 192.168.1.0/24 dev eth0

这篇文章仅仅对 ip 命令进行了一些介绍。不是要求你马上使用 ip 命令。你可以继续使用 ifconfig 。因为 ifconfig 的弃用相当的慢，很多发行版里依旧默认安装了该命令。但是相信最终会逐步被 ip 命令完全取代。看过这篇介绍，到时候你便能很快的转换过去。如果你还想了解更多 ip 命令的用法，请看 ip 命令的 man 手册。
