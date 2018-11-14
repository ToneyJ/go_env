# 安装golang环境
## 下载go语言安装包
安装包下载地址为：https://golang.org/dl/。

如果打不开可以使用这个地址：https://golang.google.cn/dl/。

## 安装命令
```shell 
sudo apt-get install bison ed gawk libc6-dev make -y //安装依赖
```
```shell
sudo tar -C /usr/local -zxf go1.10.linux-amd64.tar.gz //解压go
```
```shell
sudo vim  /etc/profile 
```
```shell
    //编辑配置文件
    export GOROOT=/usr/local/go //go的安装目录

	export PATH=$PATH:/usr/local/go/bin //go安装目目录下bin目录  

    export GOPATH=/home/itcast/go //go的工作目录

    export PATH=$GOPATH/bin/:$PATH //go的工作目录下bin目录
```
```shell
source /etc/profile     //加载配置文件
    
sudo reboot             //重启

go -env                   //测试
```
# 安装Goland
1.解压安装包
```shell
sudo tar xvfz goland-2017.3.3.tar.gz -C /opt/
```
2.进入到解压目录
```shell
cd /opt/GoLand-2017.3.3/bin/
```
3.运行golang
```shell
./goland.sh
```
4.goland桌面图标创建
复制Goland.desktop到桌面文件
右键vim打开Goland.desktop并修改
```shell
[Desktop Entry]
Name=Goland
Exec=/opt/GoLand-2018.1.4/bin/goland.sh	Icon=/opt/GoLand-2018.1.4/bin/goland.png
Type=Application
Categories=Appliction;Development;
Encoding=UTF-8
Version=2018.1.4
```
修改权限
```shell
chmod 777
```

# Goland汉化
```shell
git clone https://github.com/ewen0930/PyCharm-Chinese
cd PyCharm-Chinese/
bash package.cmd 
sudo apt install default-jdk 
sudo cp ./resources_zh.jar  /opt/GoLand-2018.1.5/lib/
```

# 配置mysql
ubuntu18.04安装mysql

	sudo dpkg -i mysql-apt-config_0.*.****_all.deb
	sudo apt-get update
	sudo apt-get install mysql-server mysql-client -y
	在安装的过程中需要输入mysql root的密码
ubuntu18.04安装libmysqlclient 驱动
	
    sudo apt-get libmysqlclient-dev

ubuntu18.04修改mysql远程连接
	
    ① 登录MySQL

	执行命令为：mysql -u root -p

	回车后输入密码

	② 选择 mysql 数据库

	执行命令为：use mysql;

	查看mysql 数据库中存储的用户信息的 user 表。

	③ 查看mysql 数据库的 user 表中当前 root 用户的相关信息

	执行命令为：select host,user,authentication_string,plugin from user;

	执行完命令后显示一个表格， root 用户的 host默认显示的 localhost，说明只支持本地访问，不允许远程访问。

	④ 更改 host 的默认配置

	执行命令为：update user set host='%' where user='root';

	⑤ 刷新

	执行命令为：flush privileges;
