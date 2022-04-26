---
title: Linux
date: 2022-04-15 13:27:15
categories:
- 运维
tags: 
- 运维
- linux
---

# 1.linux基础

## 1.目录结构



```yaml
bin:
bin为binary的简写，主要放置系统的必备执行文件，例如:
cat、cp、chmod df、dmesg、gzip、kill、ls、mkdir、more、mount、rm、su、tar等
	
/usr/bin: 
主要放置应用程序工具的必备执行文件，例如:
c++、g++、gcc、chdrv、diff、dig、du、eject、elm、free、gnome*、gzip、htpasswd、kfm、ktop、last、less、locale、m4、make、man、mcopy、ncftp、 newaliases、nslookup passwd、quota、smb*、wget		

/sbin:
主要放置系统管理的必备程序，例如:
cfdisk、dhcpcd、dump、e2fsck、fdisk、halt、ifconfig、ifup、ifdown、init、insmod、lilo、lsmod、mke2fs、modprobe、quotacheck、reboot、rmmod、 runlevel、shutdown等

/usr/sbin:
主要放置网路管理的必备程序，例如:
dhcpd、httpd、imap、in.*d、inetd、lpd、named、netconfig、nmbd、samba、sendmail、squid、swap、tcpd、tcpdump等

•主目录：/root、/home/username
•用户可执行文件：/bin、/usr/bin、/usr/local/bin
•系统可执行文件：/sbin、/usr/sbin、/usr/local/sbin
•其他挂载点：/media、/mnt
•配置：/etc
•临时文件：/tmp
•内核和Bootloader：/boot
•服务器数据：/var、/srv
•系统信息：/proc、/sys
•共享库：/lib、/usr/lib、/usr/local/lib
```

<!-- more -->

# 2.命令 



## 1.find

find ./ -name"*.jpg" -type 查找文件

find $(pwd) -name "1.jpg" 2>/dev/null

-print0 不换行输出

-printf 可以定义找到的文件的格式

"%f"只显示文件名字，不打印目录

"%h"只打印目录部分，不打印文件名

"%p"打印find注明路径之后的路径和文件

-maxdepth 查找的目录深度最多多少层，后面跟数字

-mindepth 查找的深度至少多少层

可以两个结合使用表示搜索指定层级之间的内容-path 查找目录下的文件或子目录

## 2.grep

grep  查找文件内容，相当于ctrl f

-v 反选，屏蔽

 -r  递归查询子目录

## 3.tail

待补充

## 4.xargs

待补充

## 5.exec

 以-exec开头，以\;或+结束

# 3.其他

## 1.（0，1，2）

0标准输入

1标准输出

2错误输出

所以2>/dev/null意思是错误的输出指向/dev/null这个地址,这个地址在linux中也被叫小黑洞

2>&1 | grep -v "屏蔽的内容"

意思是把错误内容也当作输出，然后通过grep -v屏蔽



# 4.快捷键

1. ctrl l 清屏

2. cd - 返回上一次停留的目录

3. history 历史命令会有一个number

   -number 显示最近n条数据

   n 显示n条以后的数据

4. ！number 快速执行history命令

5. ！！执行上一条命令

6. tail -f -n50 /filename 滚动查看指定文件
