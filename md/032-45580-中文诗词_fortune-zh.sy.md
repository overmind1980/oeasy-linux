---
show: step
version: 1.0
enable_checker: true
---

# 本章回顾

## 我们来回顾一下 😌

**上一部分我们都讲了什么？**🤔

- fortune是英文的
- 如果想来点中文的笑话或者诗歌可以么？
- 怎么来呢？🤔

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220903-1662193886249)

### 那有没有中 🀄️ 文的 fortune 呢？

```shell
# 搜索一下 fortune
apt search fortune chinese
```

- 简介里匹配也可以

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220903-1662193939927)

- 搜索到了
- 去下载吧～

###  中文 fortune

```shell
sudo apt install fortune-zh
fortune-zh
```

- /usr/share/games/fortunes/{tang300,song100}
- 这两个是中 🀄️ 文的是诗歌库
	- tang300 唐诗三百首
	- song100 一百首宋词

### pipe
- 输出重定向到 cowsay

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/shi.png)

```shell
fortune-zh tangb300 | cowsay -f beavis.zen 
```

### 彩色 🎨 的原理‼️

```shell
#进入fortunes-zh的素材文件夹
cd /usr/share/games/fortunes/
#查看素材
vi tang300
```

![tang300](https://labfile.oss.aliyuncs.com/courses/2712/tang300.jpg)

### 打开唐诗
![Image text](https://labfile.oss.aliyuncs.com/courses/2712/caise.png)

- ^[[32m《感遇·其一》^[[m
	- 这里面的^[是<kbd>esc</esc>转义字符
	- 相当于"\033"
	- [32m代表绿的字体
	- ^[[m代表回到原始字体
	- 下面的33m意味着橙色字体

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220903-1662197303288)

- 30~37 都可以设置并修改颜色 🎨
- 也可以建立自己的彩色俗语库

### 总结 🤨

- 下载了中 🀄️ 文谚语
- 输出重定向了中文谚语
- 理解词典和颜色
- 下次讲什么？🤔
- 下次再说！👋

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220903-1662197273972)
