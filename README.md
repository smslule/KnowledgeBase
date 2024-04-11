# KnowledgeBase

- 网络配置问题，主要是不能从外部局域网访问wsl网络，这使得用板子没法挂载wsl里的nfs和使用tftp，网上有些间接的办法解决了这个问题，但很麻烦，懒得去折腾

- 内存占用和硬盘存储不能自动回收，就像VirtualBox和VMWare的虚拟硬盘文件一样，会不断扩大，只能手动回收。

> wsl --update --pre-release
> 在 %userprofile%.wslconfig 中写入以下内容然后保存

```bash

[wsl2]
memory=16G  #配置虚拟机最大使用内存，按需，默认Windows主机内存的1/2
[experimental]
autoMemoryReclaim=gradual # 检测到空闲CPU使用率后自动释放缓存内存。设置gradual为缓慢释放，设置dropcache为立即释放缓存内存。
sparseVhd=true
networkingMode=mirrored # 如果值为mirrored则这将打开镜像网络模式。默认或无法识别的配置会设置为NAT。
dnsTunneling=true
firewall=true
autoProxy=true #强制WSL使用Windows的HTTP代理信息

```

> 然后启用稀疏 VHD 允许 WSL2 的硬盘空间自动回收，运行如下命令

```bash

wsl --manage 发行版名字 --set-sparse true

```

- <https://devblogs.microsoft.com/commandline/windows-subsystem-for-linux-september-2023-update/>
