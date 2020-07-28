# dd

## 依赖

```sh
apt update && apt install -y xz-utils openssl gawk file wget
yum update && yum install -y xz openssl gawk file wget
```

## 下载

```sh
wget --no-check-certificate -qO InstallNET.sh \
'https://github.com/zvg/dd/raw/master/InstallNET.sh' && \
chmod a+x InstallNET.sh
```

## Debian

* 以下命令中的 -d 后面为Debian版本号，-v 后面为64位/32位，可根据需求进行替换。

### Debian 10

```sh
bash InstallNET.sh -d 10 -v 64 -a --mirror 'http://archive.debian.org/debian/'
bash InstallNET.sh -d 10 -v 64 -a --mirror 'http://mirrors.ustc.edu.cn/debian/'
```

```sh
bash <(wget --no-check-certificate -qO- \
'https://github.com/zvg/dd/raw/master/InstallNET.sh') -d 10 -v 64 -a
```

### Debian 9

```sh
bash InstallNET.sh -d 9 -v 64 -a --mirror 'http://archive.debian.org/debian/'
bash InstallNET.sh -d 9 -v 64 -a --mirror 'http://mirrors.ustc.edu.cn/debian/'
```

```sh
bash <(wget --no-check-certificate -qO- \
'https://github.com/zvg/dd/raw/master/InstallNET.sh') -d 9 -v 64 -a
```

## CentOS

* 在有些vps上找不到硬盘ID，所以有些不成功。Vultr家家就可以
* 以下命令中的 -c 后面为CentOS版本号，-v 后面为64位/32位，可根据需求进行替换。
* Centos 7 不支持

```sh
bash InstallNET.sh -c 6.10 -v 32 -a --mirror 'http://mirror.centos.org/centos'
```

```sh
bash <(wget --no-check-certificate -qO- \
'https://github.com/zvg/dd/raw/master/InstallNET.sh') -c 6.9 -v 64 -a
```

## Ubuntu

* 以下命令中的 -u 后面为Ubuntu版本号，-v 后面为64位/32位，可根据需求进行替换。

```sh
bash InstallNET.sh -u 18.04 -v 64 -a --mirror 'http://archive.ubuntu.com/ubuntu'
bash InstallNET.sh -u 16.04 -v 64 -a --mirror 'http://archive.ubuntu.com/ubuntu'
```

```sh
bash <(wget --no-check-certificate -qO- \
'https://github.com/zvg/dd/raw/master/InstallNET.sh') -u 18.04 -v 64 -a
bash <(wget --no-check-certificate -qO- \
'https://github.com/zvg/dd/raw/master/InstallNET.sh') -u 16.04 -v 64 -a
```

## 详情

```conf
-d/--debian [dist-name]
-u/--ubuntu [dist-name]
-c/--centos [dist-version]
-v/--ver [32/i386|64/amd64]
--ip-addr/--ip-gate/--ip-mask
-apt/-yum/--mirror
-dd/--image
-a/-m

# dist-name: 发行版本代号
# dist-version: 发行版本号
# -apt/-yum/--mirror : 使用定义镜像
# -a/-m : 询问是否能进入VNC自行操作. -a 为不提示(一般用于全自动安装), -m 为提示.
```

```sh
#使用默认镜像全自动安装
bash InstallNET.sh -d 8 -v 64 -a

#使用自定义镜像全自动安装
bash InstallNET.sh -c 6.10 -v 64 -a --mirror 'http://archive.debian.org/debian/'

# 以下示例中,将X.X.X.X替换为自己的网络参数.
# --ip-addr :IP Address/IP地址
# --ip-gate :Gateway   /网关
# --ip-mask :Netmask   /子网掩码

#使用自定义镜像全自动安装
bash InstallNET.sh -d 10 -v 64 -a --mirror 'http://mirrors.ustc.edu.cn/debian/'

#使用自定义镜像自定义网络参数全自动安装
bash InstallNET.sh -d 10 -v 64 -a \
--ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x \
--mirror 'http://archive.debian.org/debian/'

#国内推荐使用USTC源
--mirror 'http://mirrors.ustc.edu.cn/debian/'
```

## 作者

* https://moeclub.org/2018/04/03/603/
