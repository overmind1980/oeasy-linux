---
show: step
version: 1.0
enable_checker: true
---

# 动态网站tomcat+数据库postgres

## 我们来回顾一下 😌

- 我们上次搭建了tomcat
- 运行了起来
- 在里面建立了自己的web application
	- oeasy
- 设置好了WEB-INF
	- web.xml
	- classes
- 然后就可以在浏览器中动态的显示信息了
- 其实我想访问数据库里面的信息
- 可能么？🤔
- 先重复地再造一个serlet

### 新servlet
- 找到目录位置

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631438956654)

- 尝试把HelloWorlExample.java复制一份
- 并进行修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631438684220)

### 修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631439046442)

- public class的名字应该和文件名一致
- 保存并退出

### 编译

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631439204865)

- 设置好classpath
- 编译java文件 
- 编译成功
- 出现了OeasyServlet.java
- 如何把这个class映射到url里面呢？
- 打开web.xml

### 回顾

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631406260957)

- 现在我们有了class
- 需要servlet name 
- 映射到url上去
- 具体怎么写呢？

### web.xml
- 把原来的内容复制出一份来
- 然后修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631440296688)

### 启动

- 重启tomcat观察
- 顺利成功
- 如果没有成功的话
- 会有错误提示
- 是不是没有找到这个url-pattern
- 是不是没有这个servlet
- 是不是没有这个class

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631440677288)

- 顺利完成后
- 我希望能用java访问postgresql数据库

### 搜索

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631441137230)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631441149209)

- 提示需要一个postgresql-jdbc驱动
- 点击链接去下载

### 下载驱动

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631441201792)

- 下载postgresql jdbc 4.2 driver
- 我把他传到了github和gitee
- 进入和classes平级的lib目录
- 一般这里放置liberies 类库
- git clone http://gitee.com/overmind1980/oeasyorg.git

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631442369128)

### 开始编程

- 把代码复制下来
- 然后回到classes
- 编辑一个jdbc.java

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631441680097)

- 注意共有类的类名和文件名一致
- 尝试编译

### 编译运行
- 编译没有遇到问题
- 但是运行遇到了问题

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631442463742)

- 原来是postgres没开

### 启动
- 如果没有装好postgres
- 就需要再重新装一下

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631442687451)

- 装好之后
- 用postgres这个用户的身份登录psql
- 回忆之前建立的database oeasy

### 表格
- oeasyorg里面的urls.csv建立的是urls这个表
- 表里面两个字段
	- topic
	- urls

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631443675676)

### 再次编译

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631443734077)

- java -cp ../lib/postgres-xx.jar:$CLASSPATH jdbc
	- java 是让java虚拟机运行class文件
	- 最后的jdbc是class的名字
	- -cp ../lib/postgres-xx.jar:$CLASSPATH
		- -cp是设置classpath
		- 后面跟的./lib/postgres-xx.jar:$CLASSPATH是具体的classpath
		- :是分隔符这部分有两部分
		- ./lib/postgres-xx.jar 是 下载的postgres的jdbc驱动程序
		- $CLASSPATH是原来的CLASSPATH
- 现在的问题是password authentication
- 密码验证失败
- 先去源程序看看

### 源程序

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444184189)

- 用户名是postgres应该没有问题
- 但是密码应该是什么？

### 搜索

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444338028)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444427459)

- 注意有两个密码
	- 一个是数据库的postgres的密码
	- 一个是系统的postgres的密码
	- 我们用的是数据库的
- 那系统的有什么用呢
- 就是一般用户想用用postgres系统用户身份做事情的时候就会用到

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444544416)

- 我们按照第一个方法来

### 修改密码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444680891)

- 我们把密码设置为oeasy@linux
- 然后去修改jdbc.java

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444735840)

### 再次编译运行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444790174)

- 这次密码认证过去了
- 但是卡在了数据库的名称
- 现在这个是testdb
- 我们的database是oeasy
- 修改源码

### 修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444904299)

- 编译运行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631444949867)

- 终于成功啦！
- 我想用一些快乐的词汇
- 但是我忍住了
- 我哭了
- 现在还不是庆祝的时候
- 我想把urls表里面的数据查询出来

### 搜索

- 搜索能力是很重要
- 真正有主见的人
- 都是会搜索的
- 相信世界也相信自己

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631445170233)

- 感觉自己充满了能量

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631445186971)

- 应该就是这样子可以查询数据库 
- 把19行到37行拿到我们的jdbc.java中

### 融合

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631445442190)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631445450099)

- 编译失败
- 不光要融合代码
- 引入的包也要融合
- 需要Statement和ResultSet

### 反复其道

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631445681696)

- 注意数据库名
- 表名
- 字段名
- 数据类型
- 我是反复了好几次才成功
- 别着急

### 最终

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631445716581)

- 最终总会成功
- 现在需要我们把这个jdbc.java和OeasyServlet.java融合到一起
- 也就是在浏览器里面把postgres里的数据表展示出来

### 整合

- 不但整合代码
- 也要整合需要用到的包

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631454705074)

### 编译

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631455024234)

- 编译没有问题
- 重启服务器

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631455044287)

- 在浏览器中访问资源

### 访问

- 当我访问 http://localhost:8080 的时候
- tomcat启动着
- 后来我访问 http://localhost:8080/oeasy/oeasy
- 服务器直接崩溃了
- http://localhost:8080 都无法访问了
- 我去看一下日志

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631455374177)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631455551365)

- 好像是postgresql 没有启动服务

### 重来

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631455630518)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210912-1631455666617)

- 顺利地读出了postgres里面的oeasy库中的urls表中的信息！！！
- 很开心！
- 可以往数据库里面插入数据么？

### 表单

- 修改oeasy.html文件

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210913-1631496752304)

- 可以看到这个表单映射到./insert
- 提交一下试试


### 映射

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210913-1631496871039)

- 现在需要一个InsertServlet.class文件
- 先复制出一个java文件
- 然后对于文件进行修改

### 程序

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210913-1631509979299)

- 类名需要修改
- 然后执行一个sql
- 把这个sql语句输出出来
- 可以在log里面找到

### 实际运行

- 可以看到插入的内容可以用/oeasy查询到
- 说明已经插入数据库

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210913-1631510253960)

- 可以做insert
- 其实也就可以执行其他的sql语句
	- delete
	- update
	- create table
	- 等等

### 总结 🤨
- 我们这次搭建了tomcat通过servlet访问postgres数据库
- 新建了一个webapp
- 在webapp下面的WEB-INF/web.xml中
	- 建立了 url-pattern 和 servlet-name 之间的关系
	- 建立了 servlet-name 和 servlet-class之间的关系
- 制作了servlet的class并且在url上验证
- 编辑 jdbc.java 成功访问了 pq数据库
- 把jdbc.java整合成一个serlvet的形式
- 不但进行select操作而且进行insert操作
- 不过多个文件访问有点麻烦
- 可以分屏么？🤔
- 下次再说！👋


