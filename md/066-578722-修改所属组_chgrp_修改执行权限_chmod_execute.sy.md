---
show: step
version: 1.0
enable_checker: true
---

# 修改文件权限(chmod)

## 回忆

- 上次研究的是权限
- 每个文件对不同用户组有不同的权限
- 角色分为
	- u 文件拥有者
	- g 文件拥有者同组其他用户
	- o 文件拥有者所属组之外的用户
	- a 所有用户
- 权限分为
	- r 读
	- w 写
	- x 执行
- 这个执行权限x怎么理解呢？

### 建立sh脚本程序

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665565888487)

- 每秒输出一次时间

```
while true
do
	echo `date "+%H:%M:%S"`
	sleep 1s
done
```

### 尝试运行

- 可以直接用sh 运行test.sh

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665566273267)

- 但是test.sh不能直接运行
- 报错是权限不够

### 添加执行权限

- 为test.sh添加了所有者的执行权限

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665566411496)

- 这个脚本程序就可以运行了
- 当前用户是shiyanlou
- 文件的所有者也是shiyanlou
- 所以程序可以执行
- 如何理解组的执行权限呢？

### 添加用户和组

- 添加两个用户
	- oeasy
	- o2z
- 添加一个组ogroup
	- 将两个用户放进组中

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665569326302)

- 切换到用户oeasy
	- 尝试复制

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665569509177)

- 但是失败了
- 这是为什么呢？

### 目录所有者

- shiyanlou的目录所有者是shiyanlou
- oeasy在这个目录里面没有写权限

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665569596626)

- 只能先进入oeasy自己的宿主目录

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665569796134)

- 完成复制工作
- 新的test2.sh所有者是oeasy
- 理论上应该可以执行

### 执行test2.sh

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665569938844)

- 确实用oeasy用户可以执行
- 因为所有者的可执行权限是开的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665570099791)

- 修改了所有者组的可执行权限之后
- o2z就可以执行这个文件了吗？

### 尝试执行

- 使用o2z账号登录后
	- 尝试执行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665570248371)

- 但是执行失败了
- 因为所属组是oeasy这个组
- 而不是ogroup这个组

### 修改组

- 使用oeasy账号登录
- 修改所属组

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665578415611)

- chgrp 进行修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665570415838)

- 现在这个文件属于ogroup这个组了
- 看看o2z能否执行

### 尝试同组执行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665570528410)

- 执行成功
- 只要是组中的就可以执行的
- 如果我把这个所属组改成shiyanlou呢？
- o2z还能执行吗？

### 再修改

- 尝试使用oeasy来修改test2.sh的所属组

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665571858063)

- 结果失败了
- oeasy用户本身和所属组shiyanlou没有任何交集
- 只能试试用shiyanlou用户来修改group

### 用shiyanlou用户修改

- 尝试用shiyanlou用户进行修改
- 还是失败了
- test2.sh目前的用户和组都和shiyanlou没有关系

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665571986907)

- 用sudo使用root权限进行修改
- 终于成功
- 目前o2z
	- 既不是所有者oeasy
	- 也不属于所属组shiyanlou
	- 再尝试使用o2z来执行

### 执行

- 查看chmod的文档

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665578658385)

- o 应该对应的就是
	- 既不属于用户
	- 也不属于用户组
- 去试试

### 先用oeasy修改权限

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665578890289)

- 修改之后
- 可以用o2z登录执行了

### o2z执行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665578962503)

- 确实是可以执行的
- 但是如果我让所有执行权限都废除
- 会如何呢？

### 取消所有执行权限

- chmod a-x test2.sh

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665579204779)

- 真的不能执行吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665579527939)

- 确实不能执行
- 能否让所有者和所属组都不能执行
- 但非所有者和所属组的o2z能执行呢？

### 验证

- 首先是给双非组添加执行权限

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665579678293)

- 确实可以的
- 只有双非组能执行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665579932446)

- 所有者和所属组都不能执行

### 总结 🤨

- 我们这次研究的是修改所属组
	- chgrp
- 通过修改文件的所属组
	- 可以控制文件的权限
- 角色依然分为
	- u 文件拥有者
	- g 文件拥有者同组其他用户
	- o 文件拥有者所属组之外的用户
	- a 所有用户
- 权限分为
	- r 读
	- w 写
	- x 执行
- 那我可以修改文件的所有者吗？🤔
- 下次再说👋