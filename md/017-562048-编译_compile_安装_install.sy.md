---
show: step
version: 1.0
enable_checker: true
---

# 本章回顾

## 我们来回顾一下 😌

- 上次了解了如何
	- 设置源
	- 换源
- 我们可以从源上下载各种好用的最新的软件
- 了解了ubuntu和debian的上下游关系
- 了解了获取源的一些方法
- 源上有源代码
- 可是github上也有源代码
- 我可以从git直接下载源代码
- 然后编译安装么？
- 小伙子，你这个想法很可怕啊？

### 找到软件

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662020700882)

- 准备克隆

### 克隆
```
git clone https://github.com/fph/bastet.git
```

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662020791014)

- 用cpp写的一个东西

### 编译
- 有些软件编译之前要先配置

```
configure
```

- 我们这个不用

```
make
```

- 编译之后出现一个bastet可执行的二进制文件

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662020910173)

- 运行bastet

### 俄罗斯方块

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662020994798)

- 可以玩
- 最后可以做一些收尾工作
	- 把他挪到/usr/local/bin
	- 把源码删除
- 这就是编译安装的过程
- 我可以用apt再安装一次么？
	- 可以
	- 但是要先关闭当前的环境

### apt安装

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662021165247)

- 这个和github那个有什么区别么？

### 查看详细

- 基本差不多

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662021250752)

- debian游戏团队觉得不错
- 放进来的
- 这东西在哪？

### 灵魂三问

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662021309190)

- 直接就把编译好的东西
- 和帮助的manual放到位置上了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662021441023)

- 自己单独一个包
- apt确实很方便
- 我们想象debian软件的maintainer都做了什么？


### package🎁

- 软件包发布的过程生命周期：

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/package-lifecycle.png)

### maintainer

- 上游作者 fph 发布 bastet 最新版
- maintainer 
	- 编译 
		- 不同的 cpu 架构要用不同的二进制文件
	- 打包更新到最新的unstable中
	- 放到debian的服务器上去
	- 过了一段时间进入stable的版本
- ubuntu从debian的服务器下载stable的版本
- 然后更新到ubuntu的源
- 清华源、阿里源同步到本地服务器
- 最终用户从源上获得最终版的软件

### 时差问题

- 比如vim的作者更新到了vim9
- maintainer放到unstable中
- 等了好久才能下载到stable中的vim9

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220901-1662022741779)

- 稳是真稳
- 稳得有点过了
- 玩的时候不用这么稳
	- 最新的vim、python、linux都可以试着编译安装一下
	- 不难
	- 而且很有成就感
- 不过维护服务器的时候必须得稳

### 两种方法比较

- 编译安装
	- 可以获得最新版的软件
	- 可以获得特定版本(tag)的软件
	- 可以获得其他架构的软件(交叉编译)
- apt 安装
	- 非常方便
	- 也可以下载源码
	- 但是版本是maintainer来控制的
	- 就像命令行版的应用商店

### 总结
- 我们这次编译安装了俄罗斯方块
- 比较两种安装软件的方法
	- 编译安装
	- apt安装
- 各有优劣
- 我们去下载一些好玩的软件吧？！🤔 
- 且听下个实验再分解！👋
