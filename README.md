# KnowledgeBase
[wsl2]
memory=16G  #配置虚拟机最大使用内存，按需，默认Windows主机内存的1/2
[experimental]
autoMemoryReclaim=gradual # 检测到空闲CPU使用率后自动释放缓存内存。设置gradual为缓慢释放，设置dropcache为立即释放缓存内存。
sparseVhd=true
networkingMode=mirrored # 如果值为mirrored则这将打开镜像网络模式。默认或无法识别的配置会设置为NAT。
dnsTunneling=true
firewall=true
autoProxy=true #强制WSL使用Windows的HTTP代理信息
