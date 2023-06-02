---
show: step
version: 1.0
enable_checker: true
---

# asciiview

## 回忆 😌

- 这次输出了中文
- 并且找到了 cowsay 的图像素材的位置 💡
- 我们能否把现实世界的 jpg 图片
- 变成ascii形式的cow文件呢？🤔

### ascii_art

- 这是一门非常年轻的亚文化

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665540053591)

- 搜索asciiart
	- 有很多有意思的asciiart 可以下载

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665540084558)

- 能否将图片 转化为asciiart 呢？


### 准备图片 

- 在本机下载图片
	- 之后上传到蓝桥云

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637204997511)

- 注意 上传的图片 在Code文件夹中
	- cd Code 可以 进入Code文件夹

- 最好选择png格式
	- 成功概率会提高

### 准备环境 aview 🅰️

```shell
sudo apt update
sudo apt install aview
sudo apt install imagemagick
```

- 下载字符画软件
	- aview
	- imagemagick

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230103-1672708464737)

### 运行程序

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/asciiview.png)

- 使用 asciiview 可以
	- 将图片 转化为 asciiart

```shell
asciiview panda.jpg
```

### 存储字符画

- 通过 查询帮助 📕
	- 发现 字符画可以
		- 保存为文本、网页等形式
- 在运行
	- asciiview xxx.png之后
	- 出现了 字符画面
	- 注意 图片中的纯黑部分 是以空格形式 来出现的
- 按下快捷键<kbd>s</kbd>
	- 会出现一个菜单
	- 如下图

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/saveImage.png)

- 然后选择Text格式
	- 选 <kbd>1</kbd>
	- 后面再设置路径
	- 一路下一步

### 保存过程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665495993965)

- 到这一步 选<kbd>8</kbd>

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496013025)

- 然后按<kbd>y</kbd>
	- 保存
	- 然后
		- 可以关闭小窗
- ls 可以看到文件了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230107-1673084190138)

- 字符画可以长什么样子呢？

### 国画风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151365586)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151346390)

### 表情风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151395424)

### 甲骨文风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151417466)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151429870)

### 线稿风格

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496088819)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496102295)

- cat 打开 这个xxx.txt
	- 观察效果 
- 可以 把这个小动物 变成 
	- cowsay可以用的 小动物吗？

### 结合 cowsay🐄

- 先找到位置

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496255713)

- 复制小动物文件

### 复制动物

```shell
# 在确认 cowsay 已经安装的情况下
cd /usr/share/cowsay/cows
# 复制一个 cow 文件
sudo cp apt.cow oeasy.cow
#使用编辑器编辑
sudo vi oeasy.cow ~/Code/ooo.txt
```

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496415681)

### 修改字符画

- 新的动物名 cat 可以用了
	- 图案 还是 原来的字符画

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496534047)

- 怎么使用diy的字符画呢？

### 替换字符画

- 在合适位置<kbd>d</kbd><kbd>G</kbd>
	- 把 原来的字符画 删除
- :r ~/Code/xxx.txt
	- 粘贴上 自己diy的 小动物字符画

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/ooo.png)

- 话语的斜线有点问题

### 修改

- 修改文字泡泡线

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496875972)

- 注意!
	- 前5行和最后一行
	- 都是有意义的
	- 是cowsay的结构

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496842742)

### 是不能丢的东西

- 第1行和最后一行的相关头尾不能丢
	- 还有中间的有些替换字符也要注意
	- 才能保证.cow文件可用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211008-1633663823279)

- 如果要说的话比较多
	- 就需要角色要变小一点

### 角色大小选择

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205472280)

- 可以设置分辨率为四分之一大小

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205511652)



### 总结 🤨

- asciiview把图像转化为了 ascii🅰️ 字符画
- 并且修改了 cowsay 的图像素材 💡
- 我们能让 cowsay 随机讲讲笑话吗？
- 下次再说！👋
