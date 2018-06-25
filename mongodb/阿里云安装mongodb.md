参考文档：  https://blog.csdn.net/gaoyan2011/article/details/79420034

因为官方网站安装时下载速度很慢，基本下载不下来，所以把源替换为国内阿里云的源: 


### 第1步：导入公钥

```bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5  

```

### 第2步：创建源文件

```bash
ubuntu 16
echo "deb [ arch=amd64,arm64 ] http://mirrors.aliyun.com/mongodb/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list  

```

### 第3步：

```bash
sudo apt-get update  

```

### 第4步：

```bash
sudo apt-get install -y mongodb-org  

```

### >安装指定版本3.6.2


```bash
sudo apt-get install -y mongodb-org=3.6.2 mongodb-org-server=3.6.2 mongodb-org-shell=3.6.2 mongodb-org-mongos=3.6.2 mongodb-org-tools=3.6.2  


```
