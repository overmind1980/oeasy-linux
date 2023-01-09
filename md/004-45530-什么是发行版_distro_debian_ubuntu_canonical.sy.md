---
show: step
version: 1.0
enable_checker: true
---

# 查看发行版 distro

## 回忆上次内容 😌

- 计算机本身的特性决定
  - 计算机保存传递的是电子
  - 而不是原子
  - 这就使得存储和分发的成本几乎为零
- 在这样的物理基础上
	- 出现了自由软件运动
	- 从rms提出的free software 开始
	- 到gnu研发的各种软件
- 自由软件运动之后出现了开源运动
	- 提倡把源代码开放
	- 也被大量的商业公司所跟随
- github可以在全世界范围内进行协作
- linux是5000个极客一起协作出来的内核
- 除了内核之外
- 程序要运行还需要一个壳子
- 具体是什么呢？🤔

### 查看发行版

```shell
uname --help
```
- uname -a 
	- 可以得到全部信息
	- 还知道有 ubuntu 这个发行版(distro)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210909-1631155355031)

- ubuntu 就是一个壳子(发行版)
	- 那么，什么是发行版呢？

## 发行版

- 只靠 linux 内核
	- 我们无法做任何事情
- 只有内核和各种应用程序在一起
	- 我们才能使用
- 发行版就是distro
	- distro 的英文原文是 distribution
	- 是内核和应用程序的集合

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220831-1661934313987)

- 一个典型的 Linux 发行版包括
	- Linux 内核
	- 一些 GNU 程序库和工具
	- 命令行 shell
	- 也会包含图形界面。

### 都有哪些发行版呢？🤔

- 发行版非常多
	- 你可以去 [distrowatch](https://distrowatch.com/)
	- 去看看各种各样的发行版的流行趋势！

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220831-1661934219945)

- 也可以看到
	- 当前各种发行版的排名
	- 搜索感兴趣的发行版！🤪

### Distro hop

- **来做个 Distro hop**
- Distro hop 是指折腾 Distro 来玩的人

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220831-1661934491500)

- 您可以直接在 [DestroTest](https://distrotest.net/) 
	- 浏览器里开一个虚拟机
	- 直接跑各种各样的发行版

### 排名

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/distro_rank.png)

- 我应该如何选择自己的发行版呢？🤔

### 选择

- 我们可以去内核官网
	- 看看 [linux 内核对于各种发行版的吐槽](http://mirrors.kernel.org/)
	- 内核对于发行版的吐槽
	- 官方吐槽最为致命

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/tuxrardar.jpg)

- 不同的发行版有不同的技能：
	- debian, 适合系统管理和运维
	- ubuntu 安装简单，界面友好，社区活跃。
	- kali 就适合做网络安全方面的操作
	- deepin 国产的深度发行版，界面做的非常好看
	- centos 服务器
	- gentoo 深入底层，透明

### 辅助

- 这里还有个网站能根据您回答问题的情况
	- 帮您选个 distro 🤪
	- [distrochooser](https://distrochooser.de/zh-cn/)

- 发行版这么多
	- 这么乱
	- 没有头绪啊 😭
- 没关系
	- 不要着急我帮您来梳理一下
- 🧐

### Linux 发行版三大家族

- Linux 发行版虽然很多，但是大体上是三大家族：
	- Debian 家族
	- Rhel 家族
	- Suse 家族

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/distro_family.jpg)

我们分别来说一下：

## 发行版家族关系大梳理 🧐

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/GNU_Linux_Distributions_Timeline.jpg)


[查看原图](https://upload.wikimedia.org/wikipedia/commons/1/1b/Linux_Distribution_Timeline.svg)

### 详细发展过程

- 这图里面内容太多了
	- 我们再梳理一下
	- 那么应该从哪个发行版衍生呢？
- 开门见山
- debian🧐

## debian家族

- **debian 家族** **debian['dɛbɪən]**
	- [debian](https://www.debian.org/) 是免费发行版
	- 1993.12 月第一次出现
- Ian Murdock 依据
	- 他女朋友的名字 Debra Lynn 
	- 他自己的名字 Ian Murdock
	- 最终叫做“Debian”
- 各版本代号
	- 来自于玩具总动员中的角色
- Debian 是一个独立的组织
	- 组织着 5 万个以上的软件包
	- 320 百万行代码
	- 各种项目的负责人是社区选出来的

- 支持的 cpu 指令集架构也多
	- 比如中科院华为阿里押宝的 risc-v
	- 比如龙芯兼容的 mips

- 下图是他下载 cd 的截图：

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/debian_architecture.png)

- debian家族成员很多
- 比如Ubuntu😊

###  Ubuntu
- 其名称来自非洲 🌍 南部祖鲁语或豪萨语的“ubuntu"一词
	- 意思是“人性”“我的存在是因为大家的存在"
	- 是非洲传统的一种价值观。
	- 发作“oo-boon-too”的音
	- 如果你喜欢添加一些非洲撒哈拉的味道
	- 你可以在第一个"u"後面带些嗡嗡声
		- oom-boon-too😮
		- 比较上头	


![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220831-1661936414888)

- 自 2004 年创建 Ubuntu 以来
	- Mark Shuttleworth 让开放自由的开源软件被大众熟知
	- Canonical 公司运营这个ubuntu
- Canonical什么意思呢？

### 词源

- 源于希腊语芦苇κανὼν
	- reed sea
	- 芦苇之海

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672458976117)

- cane 
	- 植物的茎
	- 芦苇

### 手杖

- cane 
	- 文明棍
	- 法杖
	- 权杖
		- 度量的标准
			- 两庹一丈不是很精确
			- 得有统一标准
			- 能服众

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672481725724)

- can
	- 有能力丈量土地的人
		- 老丈人
		- 丈夫

- cunning 
	- 灵巧的
	- 狡猾的
	- 有知识的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672476933703)

- gun
	- 枪也是棍子形状的
	- 从长枪发展而来
- candy
	- suger cane
	- 甜的植物的茎(甘蔗)
	- 糖果

### 芦苇中间是空的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672458870597)

- can 
	- 罐子
- canoe
	- 中空的小船
- cannon
	- 加农炮

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672481021857)

- canel
	- 输水管道
- channel
	- 自然而形成的输水管道
	- 海峡
	- 渠道
	- 频率的渠道
- canyon
	- 峡谷

### 控制器

- 织布机控制器来自于芦苇

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672459662444)

- κανὼν 
	- 切换奇偶经线上的芦苇(Reed)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672461645497)

- 通过这个控制经线

### 偶

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672490696536)

- even 始终是 even(平)的
	- 偶数的
	- 成对的
	- 对称的
	- 稳稳当当的

### 奇

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672490985283)

- 第三个人出现
	- 一人行则得其友
	- 三人行则损一人

### 具体到织布机

- odd 一会儿 高于 even

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672491268250)

- odd 一会儿 低于 even

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672491284624)

- odd
	- 不平的
	- 相对even来说不正常的

- πηνίον 
	- 纬线穿梭子


### 经典canon

- 特指
	- 圣经
	- 督教圣经正典共有66卷（旧约39卷，新约27卷）


![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672457679173)

- 也指
	- 教会的法令，教会对于圣经的解释
	- 神职人员、教士

### 法律、规范、原则

- law、norm、principle

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672482399901)

- 音乐中的卡农
	- 原本叫做chase
	- 后来因为后面声部的规范性
	- 被叫做canon

### canonical

- canonical 来自于 canon
	- 典型的; 
	- 被收入真经篇目的; 
	- 经典的; 
	- 按照基督教会教规的; 
	- (数学表达式)最简洁的;
	- (布道时应穿的)法衣;

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672482552616)

- 公司是要传道的
	- 那资金从哪里来？

### 总结
- 我们使用
	- uname -a
	- 可以查看系统详细信息
	- 除了内核之外
	- 还有发行版
- 研究了linux发行版
	- distro
- 研究了Debian家族
	- 以及ubuntu
- ubuntu来自于canonical(经典)公司
- 这个公司怎么挣钱呢？🤔
- 下次再说👋🏻
