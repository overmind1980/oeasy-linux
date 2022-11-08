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

### 下载 aview 🅰️

- 下载字符画软件包 aview、imagemagick。

```shell
sudo apt update
sudo apt install aview
sudo apt install imagemagick
```

- aview 只接受专门的格式。
- 使用 asciiview 可以转化格式。
- bmp 格式更容易被接受。⚠

```shell
asciiview panda.jpg
```

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/asciiview.png)

- 可以在本机下载之后
- 上传到蓝桥云

### 下载图片 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637204997511)

- 注意上传的图片在Code文件夹中
- 注意图片中的纯黑部分是以空格来出现的

### 存储字符画

- 通过查询帮助 📕
- 发现字符画可以保存
- 可以把字符画保存为文本、网页等形式
- 在运行完asciiview之后
- 出现了字符画面
- 按下快捷键<kbd>s</kbd>
- 会出现一个菜单
- 如下图


![Image text](https://labfile.oss.aliyuncs.com/courses/2712/saveImage.png)

- 然后选择Text格式
	- 选 1
	- 后面再设置路径
	- 一路下一步

### 保存过程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665495993965)

- 到这一步选8

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496013025)

- 然后按y
	- 保存
- 然后可以关闭小窗
- ll可以看到文件了
- 字符画的效果需要具体实践验证

### 国画风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151365586)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151346390)

### 表情风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151395424)

### 甲骨文风

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151417466)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220428-1651151429870)

### 大小选择
![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205472280)

- 可以设置分辨率为四分之一大小

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205511652)

### 线稿风格

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496088819)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496102295)

### 结合 cowsay🐄

- 先找到位置

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496255713)

- 尝试复制小动物

### 复制动物

```shell
# 在确认 cowsay 已经安装的情况下
cd /usr/share/cowsay/cows
# 复制一个 cow 文件
sudo cp apt.cow oeasy.cow
#是用编辑器编辑
sudo vi oeasy.cow ~/Code/ooo.txt
```

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496415681)

### 修改字符画

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496534047)

- 这是原来的字符画
- 把原来的字符画删除
- 配合上自己的字符画
- 然后输出

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/ooo.png)

- 注意可以有一些修改

### 修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496875972)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496842742)

### 注意
- 不能丢的东西

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211008-1633663823279)

- 第1行和最后一行的相关头尾不能丢
- 还有中间的有些替换字符也要注意
- 才能保证.cow文件可用

### 总结 🤨

- asciiview把图像转化为了 ascii🅰️ 字符画
- 并且修改了 cowsay 的图像素材 💡
- 我们能让 cowsay 随机讲讲笑话吗？
- 下次再说！👋
