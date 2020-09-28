# InstallNET
Debian/Ubuntu/CentOS 网络安装/网络重装/纯净安装 一键脚本

## 下载脚本
```
wget --no-check-certificate -qO InstallNET.sh 'https://github.com/Zalazy/InstallNET/raw/master/InstallNET.sh' && chmod a+x InstallNET.sh
```

默认密码：MoeClub.org

确保安装了所需软件

### Debian / Ubuntu：

```
apt-get -y install xz-utils openssl gawk file
```

### RedHat / CentOS：

```
yum -y install xz openssl gawk file
```

### Usage：
```
        bash InstallNET.sh      -d/--debian [dist-name]
                                -u/--ubuntu [dist-name]
                                -c/--centos [dist-version]
                                -v/--ver [32/i386|64/amd64]
                                --ip-addr/--ip-gate/--ip-mask
                                -apt/-yum/--mirror
                                -dd/--image
                                -a/-m
```

dist-name：发行版本代号

dist-version：发行版本号

-apt/-yum/--mirror：使用定义镜像

-a/-m：询问是否能进入VNC自行操作，-a 为不提示(一般用于全自动安装)，-m 为提示

## 开始安装

### 使用默认镜像全自动安装：

```
bash InstallNET.sh -d buster -v amd64 -a
```

### 使用自定义镜像全自动安装：

```
bash InstallNET.sh -d buster -v amd64 -a --mirror 'https://mirrors.tuna.tsinghua.edu.cn/debian/'
```

以下示例中，将X.X.X.X替换为自己的网络参数

--ip-addr：IP Address    /IP地址

--ip-gate：Gateway       /网关

--ip-mask：Netmask       /子网掩码

### 使用自定义镜像自定义网络参数全自动安装：

```
bash InstallNET.sh -d buster -v amd64 -a --ip-addr 192.168.1.2 --ip-gate 192.168.1.1 --ip-mask 255.255.255.0 --mirror 'https://mirrors.tuna.tsinghua.edu.cn/debian/'
```

### 使用自定义网络参数全自动dd方式安装：

```
bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'https://moeclub.org/onedrive/IMAGE/Windows/win7emb_x86.tar.gz'
```

### 使用自定义网络参数全自动dd方式安装存储在谷歌网盘中的镜像(调用文件ID的方式)：

```
bash InstallNET.sh --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd "https://image.moeclub.org/GoogleDrive/1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J"
```
