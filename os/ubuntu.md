# Ubuntu

## Ubuntu Source

> Backup sources list.
```shell
sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak
sudo vi /etc/apt/sources.list
```

> Update with following:

```
# 中科大
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src https://mirrors.ustc.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse

# 163
deb http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ bionic-backports main restricted universe multiverse

# 清华
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-updates main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-backports main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-security main restricted universe multiverse
deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ bionic-proposed main restricted universe multiverse

# 阿里云
deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
```

## Ubuntu Change Hostname

在Ubuntu系统中，快速查看主机名有多种方法：
其一，打开一个GNOME终端窗口，在命令提示符中可以看到主机名，主机名通常位于“@”符号后；
其二，在终端窗口中输入命令：hostname或uname –n，均可以查看到当前主机的主机名。

2、临时修改主机名

命令行下运行命令：“hostname 新主机名”
其中“新主机名”可以用任何合法字符串来表示。不过采用这种方式，新主机名并不保存在系统中，重启系统后主机名将恢复为原先的主机名称。
例子：hostname ubuntu-temp
这样主机名字就临时被修改为ubuntu-temp，但是终端下不会立即显示生效后的主机名，重开一个终端窗口(通过ssh连接的终端需要重新连接才可以);

http://hovertree.com/menu/ubuntu/
3、永久修改主机名

在Ubuntu系统中永久修改主机名也比较简单。主机名存放在/etc/hostname文件中，修改主机名时，编辑hostname文件，在文件中输入新的主机名并保存该文件即可。重启系统后，参照上面介绍的快速查看主机名的办法来确认主机名有没有修改成功。

值的指出的是，在其它Linux发行版中，并非都存在/etc/hostname文件。如Fedora发行版将主机名存放在/etc/sysconfig/network文件中。所以，修改主机名时应注意区分是哪种Linux发行版。

3、/etc/hostname与/etc/hosts的区别
/etc/hostname中存放的是主机名，hostname文件的一个例子：
v-jiwan-ubuntu-temp

/etc/hosts存放的是域名与ip的对应关系，域名与主机名没有任何关系，你可以为任何一个IP指定任意一个名字，hostname文件的一个例子：
127.0.0.1       localhost
127.0.1.1       v-jiwan-ubuntu


## Ubuntu系统时间相差8小时解决方法

```shell
sudo timedatectl set-local-rtc 1 
```
