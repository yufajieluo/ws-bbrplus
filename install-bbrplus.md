# BBRPLUS
## 1.安装BBRPLUS
### 1.1 安装内核
```
https://raw.githubusercontent.com/yufajieluo/ws-bbrplus/master/kernel-4.14.129-bbrplus.rpm

yum install -y kernel-4.14.129-bbrplus.rpm
```

### 1.2 切换启动内核
```
grub2-set-default 'CentOS Linux (4.14.129-bbrplus) 7 (Core)'
```

### 1.3 修改sysctl.conf
```
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf

echo "net.ipv4.tcp_congestion_control=bbrplus" >> /etc/sysctl.conf
```

### 1.4 重启机器
```
reboot
```

### 1.5 检查内核
```
uname -r
```

### 1.6 检查BBRPLUS启动
```
lsmod | grep bbrplus
```

## 2.卸载BBRPLUS
### 2.1 修改sysctl.conf
```
#net.core.default_qdisc=fq

#net.ipv4.tcp_congestion_control=bbrplus
```
> 注释掉

### 2.2 生效并重启
```
sysctl -p

reboot
```
### 2.3 检查内核
```
uname -r
```
