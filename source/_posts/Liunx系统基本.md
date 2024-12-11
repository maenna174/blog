---
title: Liunx系统基本
date: 2024-12-11 20:16:03
tags: 
- Liunx
---
**Liunx系统中一切皆文件** 
## 文件名及其作用 
/bin 存放命令（系统）  
/boot 乌班图核心镜象文件  
/cdrom 光驱  
/dev 设备  
/etc 环境（进行设置）  
/home 用户的文件（音乐、文档…）  
/lib（依赖）文件依赖、数据依赖  
/media 媒体设备  
/mnt 挂载临时存储（U盘等）  
/opt 安装软件  
/proc 内存  
/root（防止误操）  
/run 运行程序  
/sbin 超级命令（支持系统运行）  
/snop 快照  
/srv 系统的运行文件  
/var 运行时发生情况的文件  
/tmp 临时文件（不久后自己清除）  
/sys 操作系统系统文件  
/user 大家都可以使用的

## 系统管理操作． 
### 关闭防火墙
#### systemctl
基本语法
systemctl start / stop / restart / status  
服务名查找 /usor/lib/systemd/system  
实操 sudo systemctl stop NetworkManager
（停止网络服务）  
### 关机和重启
halt 关闭系统不断电  
power off 关闭系统并断电 等同于 shutdown-h now   
reboot 重启 等同于 shutdown-r now  
sudo shutdown-h 1 （1分钟之后关闭）
### 修改主机名
sudo hostname --static set-hostname 名字
### 查看手册页说明文档
man 命令  
操作手册 man man.  
### 快捷键  
ctrl + c 停止进程  
ctrl + l 清屏；彻底清屏是reset 退出  
ctrl + q 退出   
运用Tap键 提示（更重要的是可以防止敲错）  
上下键 查找执行过的命令  
ctrl + u  清除当前敲的命令
### 常用命令
pwd : print working directory 打印工作目录  
**Is** 
1. Is-l 列出目录内容 (l-l)
2. Is-a 显标隐藏文件（开头文件）  

### cd: Change Directory 切换路径．  

| 代码| 作用           |
| ---| ---            |
| cd |绝对路径 切换路径 |
| cd |相对路径 切换路径 |
| cd~ 或者cd |回到自己的家目录|
| cd- |回到上一次所在的录|
| cd.. |回到当前目录的上一级录|
| cd-|跳转到实际物理路径而非快捷方式路径|  

### mkdir:Make directory 建立目录．
mkdir + 文件名称
mkdir -p 名／名／名 （创建多层文件夹）

### touch 创建空白文件  
touch 文件名称．  
例 touch xiyou/sunwukong.txt
### cp 复制文件或目录
cp［选项］ Sourse dest（复制source文件到dest）  
-r 递归复制整个文件夹
