---
show: step
version: 1.0
enable_checker: true
---

# 软连接ln

## 回忆

- 上次我们学习了cp命令
- cp有两个关键因素
	- 源
	- 目标
- 源和目标都可以用绝对路径和可以用相对路径
	- 绝对路径
		- 清晰
		- 但一般比较长
	- 相对路径
		- 较短
		- 但头脑一定要清晰
- cp 还有一些参数
	- -r 递归
	- -f 强制
	- -i 交互
	- -l 只生成链接
- 这个链接是什么意思呢？

### 例子

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663135201101)

- /usr/bin/python 是一个链接
	- 是一个指向/usr/bin/python2.7的链接

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663135225246)

- 运行python
- 就是运行/usr/bin/python3
- 那什么是一个链接呢？

### 链接

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663135971983)

- 链接和inode有关
- 这个单词好像在ls中见过

### 查看inode

```
man ls
```

- 查看ls帮助

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663135368815)

- ls -i 
	- 可以查询到文件的inode
	- inode就是index node
	- 索引节点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663135820024)

- 这两个东西的inode不同
- 我可以自己建立软硬的链接吗？

### 查询文档

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663136426053)

- 灵魂三问之后
- 查看文档手册

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663136387810)

### 动手试试

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663136578600)

- 可以看到我们建立了一个硬链接
- 这两个文件所指向的索引节点(inode)一样
- 那么如何建立一个软链接呢

### 查询文档

- 参数为-s

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663136713582)

- 软链接也叫符号链接
- symbolic link

### 软链接

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663136825827)

- 可以看到软链接就是箭头的那种形式
- python是python2.7的软链接
- 而且软链接使用的inode不同
- 那删除文件会如何呢？

### 删除链接

- 分别删除硬链接和软链接

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663137559200)

- 就像一般删除文件一样
- 没有区别
- 删除被链接文件会如何呢

### 删除被链接的文件

- 将源删除

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663137635548)

- 硬链接还在还能用
- 软链接已经不能用了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220914-1663137683556)

- 找不到了
- 层层叠叠的链接
- 如何一下子找到源呢？

### readlink

- 读取链接的源
	- readlink
- 读取链接的根源
	- readlink -f

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672492321832)

- 这个命令和realpath很像啊

### readlink 和 realpath

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672493436331)

- 这两个帮助很像

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672493451288)

- 可以直接拷贝根源吗？

### 查询文档

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221231-1672493314825)

- 那么我们cp -l 生成的是什么链接呢？

### cp -l

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221119-1668821764480)

- 看起来cp -l拷贝的是一个硬链接


### 总结 
- 这次我们研究了ln
- ln指的是链接(link)
- 可以建立硬链接、软链接
- 硬链接
	- 直接指向原来文件所在的硬盘位置
	- 指向索引节点(inode)
	- 索引节点被引用数量+1
	- 如果源文件被删除
	- 硬链接仍然指向索引节点(inode)
- 软链接
	- 指向原来的文件而不是索引节点
	- 所以如果源文件被删除
	- 软链接指向目标消失
	- 也就失效了
- cp -l 拷贝的是一个硬链接
- 如果我只想拷贝文件中的内容
	- 而不关心文件的各种信息
	- 有什么好方法吗？🤔
- 下次再说👋
就可以