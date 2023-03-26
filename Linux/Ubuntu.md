# 软件包管理器

## DPKG

```shell
dpkg -i <.deb file name>              # 安装软件
dpkg -R <directory>                   # 安装一个目录下面所有的软件包
dpkg -r <package_file>                # 删除软件包（保留配置信息）   
dpkg -P <package_file>                # 删除软件包（包括配置信息）
dpkg –-unpack <package_file>          # 释放软件包，但是不进行配置，可以和-R一起使用
dpkg –configure <package_file>        # 重新配置和释放软件包，和-a一起使用，将配置所有没有配置的软件包
```

## APT

镜像站点地址管理，/etc/apt/sources.list

```shell
sudo apt-get update                  # 更新可用软件包列表
sudo apt-get upgrade                 # 升级所有有可用更新的软件包(通过安装/升级来更新系统)
sudo apt-get full-upgrade            # 完全升级已安装的软件包（通过卸载/安装/升级来更新系统）
sudo apt-get dist-upgrade            # 将系统升级到新版本

sudo apt install <package_name>      # 安装软件包，可以指定多个包，以空格分隔
sudo apt install <package_name>=<version_number>    # 安装软件的特定版本
sudo apt reinstall <package_name>    # 重新安装软件包
sudo apt remove <package_name>       # 移除软件包（保留配置文档）
sudo apt purge <package_name>        # 移除软件包（删除配置文档）
sudo apt list                        # 列出所有可用的软件包
sudo apt list | grep <package_name>  # 使用grep命令过滤输出
```

# 环境变量

```shell
export                                             # 显示当前系统定义的所有环境变量
echo $PATH                                         # 输出当前PATH环境变量
```

## 临时环境变量


```shell
export PATH=$PATH:/work/platform-tools             # 配置platform-tools环境变量
```

- 生效时间：立即生效
- 生效期限：当前终端有效，窗口关闭后无效
- 生效范围：仅对当前用户有效
- 配置的环境变量中不要忘了加上原来的配置，即`$PATH`部分，避免覆盖原来配置

## 修改用户环境变量

- 生效期限：永久有效
- 生效范围：仅对当前用户有效

### ~/.bashrc

```shell
vim ~/.bashrc
export PATH=$PATH:/work/platform-tools             # 加在~/.bashrc文件最后一行
```

- 使用相同用户打开新终端时生效或手动`source ~/.bashrc`生效
- 如果有后续的环境变量加载文件覆盖了PATH定义，则可能不生效

### ~/.bash_profile

```shell
vim ~/.bash_profile
export PATH=$PATH:/work/platform-tools             # 加在~/.bash_profile文件最后一行
```

- 使用相同用户打开新终端时生效或手动`source ~/.bash_profile`生效
- 如果没有`~/.bash_profile`文件，则可以编辑`~/.profile`文件或者新建一个

## 修改系统环境变量

- 生效期限：永久有效
- 生效范围：对所有用户有效

### /etc/bash.bashrc

```shell
vim /etc/bash.bashrc
export PATH=$PATH:/work/platform-tools             # 加在/etc/bash.bashrc文件最后一行
```

新开终端或手动`source /etc/bash.bashrc`生效

### /etc/profile

```shell
vim /etc/profile
export PATH=$PATH:/work/platform-tools             # 加在/etc/profile文件最后一行
```

新开终端或手动`source /etc/profile`生效

### /etc/environment

```shell
vim /etc/environment
export PATH=$PATH:/work/platform-tools             # 加在/etc/environment文件最后一行
```

新开终端或手动`source /etc/environment`生效

## 生效原理

- 系统环境变量 ----> 用户自定义环境变量 

- `/etc/environment` ---->`/etc/profile` ----> `~/.profile`

- `/etc/profile`会加载`/etc/bash.bashrc`文件，然后检查`/etc/profile.d/`目录下的`.sh`文件并加载

- `~/.profile`只在用户登录的时候读取一次，`/.bashrc`会在每次运行`Shell`脚本的时候读取一次

- 可以自定义一个环境变量文件
  - 在某个项目下定义`uusama.profile`
  - 在这个文件中使用`export`定义一系列变量
  - 在`~/.profile`文件后面加上：`sourc uus`
  - `ama.profile`
  - 这样每次登陆都可以在`Shell`脚本中使用自己定义的一系列变量

# adb/fastboot

## no permissions (user in plugdev group; are your udev rules wrong?)解决方案

**查看自己的安卓设备**

```shell
test@test:~$ lsusb
Bus 001 Device 005: ID 18d1:4ee0 Google Inc. 
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 002 Device 003: ID 0e0f:0002 VMware, Inc. Virtual USB Hub
Bus 002 Device 002: ID 0e0f:0003 VMware, Inc. Virtual Mouse
Bus 002 Device 001: ID 1d6b:0001 Linux Foundation 1.1 root hub
```

**创建设备文件(文件名随便)**

```shell
sudo vim /etc/udev/rules.d/90-android.rules

SUBSYSTEM=="usb",ATTRS{idVendor}=="18d1",ATTRS{idProduct}=="4ee0",MODE="0666",GROUP="plugdev",SYMLINK+="android",SYMLINK+="android_adb"
```

 **重启adb服务**

```shell
sudo udevadm control --reload-rules
sudo service udev restart
sudo udevadm trigger
adb kill-server
adb start-server
```