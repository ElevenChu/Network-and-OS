## Linux概述

### 什么是Linux？

: Linux是一套免费使用和自由传播的类Unix操作系统，是一个基于POSIX和Unix的多用户、多任务、支持多线程和多CPU的操作系统。它能运行主要的Unix工具软件、应用程序和网络协议。它支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。

### 什么是Linux内核？
:Linux 系统的核心是内核。内核控制着计算机系统上的所有硬件和软件，在必要时分配硬件，并根据需要执行软件。
![image](https://user-images.githubusercontent.com/57619422/133041324-7f9dbaed-44e4-4965-b287-cefccaf331b1.png)

### Linux的基本组件
:就像任何其他典型的操作系统一样，Linux拥有所有这些组件：内核，shell和GUI，系统实用程序和应用程序。Linux比其他操作系统更具优势的是每个方面都附带其他功能，所有代码都可以免费下载。

### Linux 的体系结构
: 从大的方面讲，Linux 体系结构可以分为两块

![277299d10f0f977371e2a7a162b30cfb_watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1RoaW5rV29u,size_16,color_FFFFFF,t_70](https://user-images.githubusercontent.com/57619422/133041538-af094d12-8a3d-460c-b962-e12e27926f82.png)

- 用户空间(User Space) ：用户空间又包括用户的应用程序(User Applications)、C 库(C Library) 。

- 内核空间(Kernel Space) ：内核空间又包括系统调用接口(System Call Interface)、内核(Kernel)、平台架构相关的代码(Architecture-Dependent Kernel Code) 。

### BASH和DOS之间的基本区别是什么？

![image](https://user-images.githubusercontent.com/57619422/133041854-6b405c3d-a175-459a-a0b1-ca0cee508164.png)


### Linux系统缺省的运行级别

![image](https://user-images.githubusercontent.com/57619422/133042577-a5d58a74-5ce6-4182-9d43-4dcd616fcf9c.png)


### Linux使用的进程间通信方式
![image](https://user-images.githubusercontent.com/57619422/133042963-0e359a81-e119-4800-8480-0bb7f36736e5.png)


### 什么是交换空间？
:交换空间是Linux使用的一定空间，用于临时保存一些并发运行的程序。当RAM没有足够的内存来容纳正在执行的所有程序时，就会发生这种情况

### 什么是GUI？
:图形用户界面（Graphical User Interface，简称 GUI，又称图形用户接口）是指采用图形方式显示的计算机操作用户界面。


## 磁盘，目录和文件

在 Linux 操作系统中，所有被操作系统管理的资源，例如网络接口卡、磁盘驱动器、打印机、输入输出设备、普通文件或是目录都被看作是一个文件。

Linux系统中有一个重要概念 **一切都是文件** 

![ecbb9743a1e815d27a7193b58cf67cbe_format,png](https://user-images.githubusercontent.com/57619422/133045103-9f036ed8-ab54-45ad-b2b1-10881a80c5ec.png)

### 什么是硬链接和软链接？

- 硬链接 : 由于 Linux 下的文件是通过索引节点(inode)来识别文件，硬链接可以认为是一个指针，指向文件索引节点的指针，系统并不为它重新分配 inode 。每添加一个一个硬链接，文件的链接数就加1。

不足：1）不可以在不同文件系统的文件间建立链接；2）只有超级用户才可以为目录创建硬链接。

- 软链接： 软链接克服了硬链接的不足，没有任何文件系统的限制，任何用户可以创建指向目录的符号链接。因而现在更为广泛使用，它具有更大的灵活性，甚至可以跨越不同机器、不同网络对文件进行链接。

不足：因为链接文件包含有原文件的路径信息，所以当原文件从一个目录下移到其他目录中，再访问链接文件，系统就找不到了，而硬链接就没有这个缺陷，你想怎么移就怎么移；还有它要系统分配额外的空间用于建立新的索引节点和保存原文件的路径。


![image](https://user-images.githubusercontent.com/57619422/133045704-6fc7c19e-d2a6-4a4e-b92c-368edcfcecc2.png)

### 什么是RAID?

:RAID 全称为独立磁盘冗余阵列(Redundant Array of Independent Disks)，基本思想就是把多个相对便宜的硬盘组合起来，成为一个硬盘阵列组，使性能达到甚至超过一个价格昂贵、 容量巨大的硬盘。RAID 通常被用在服务器电脑上，使用完全相同的硬盘组成一个逻辑扇区，因此操作系统只会把它当做一个硬盘。

RAID 分为不同的等级，各个不同的等级均在数据可靠性及读写性能上做了不同的权衡。在实际应用中，可以依据自己的实际需求选择不同的 RAID 方案。

## 安全

###  一台 Linux 系统初始化环境后需要做一些什么安全工作？

![image](https://user-images.githubusercontent.com/57619422/133047364-0b2d7c7a-588b-416a-8a05-559d517de2ce.png)

### 什么叫CC攻击?什么叫DDOS攻击？

- CC 攻击，主要是用来攻击页面的，模拟多个用户不停的对你的页面进行访问，从而使你的系统资源消耗殆尽。

- DDOS 攻击，中文名叫分布式拒绝服务攻击，指借助服务器技术将多个计算机联合起来作为攻击平台，来对一个或多个目标发动 DDOS 攻击。

攻击：即是通过大量合法的请求占用大量网络资源，以达到瘫痪网络的目的

### 怎么预防CC攻击和DDOS攻击？

：防 CC、DDOS 攻击，这些只能是用硬件防火墙做流量清洗，将攻击流量引入黑洞。

（流量清洗这一块，主要是买 ISP 服务商的防攻击的服务就可以，机房一般有空余流量，我们一般是买服务，毕竟攻击不会是持续长时间）

### 什么是网站数据库注入?
![image](https://user-images.githubusercontent.com/57619422/133048027-e2785433-c9d3-45a3-a248-42d3775bf9ab.png)

### 如何过滤和预防

- 1.后台权限设置分明，普通用户与系统管理员、超级管理员的权限严格的区分开来
- 
- 2.加强验证码输入防护措施:验证码的输入可以很好的防止数据库被注入的情况的发生，一是加强对用户输入内容的检查与验证; 二是强迫使用参数化语句来传递用户输入的内容。始终通过测试类型、长度、格式和范围来验证用户输入，过滤用户输入的内容。这是防止SQL注入式攻击的常见并且行之有效的措施。

-3.使用数据库如mysql自带的安全参数
































