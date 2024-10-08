### Git 基本操作

#### -  Git是一个分布式版本控制工具

把所有版本全部分布存放在各自电脑上，每台电脑上都有一个完整版本，即使某个电脑挂掉，不影响代码完整性

### 1. 快速入门

想要让Git对一个目录进行版本控制需要以下步骤：

- 进入要管理的文件夹
- 执行初始化命令

```
git init
```

- 管理目录下的文件状态

```
git status

注: 新增的文件和修改过后的文件都是红色
```

- 管理指定的文件(红变绿)

```
git add 文件名
git add .
```

- 个人信息配置 ： 用户名，邮箱 【一次即可】

```
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
```

- 生成版本

```
git commit -m '描述信息'
```

- 查看版本记录

```
git log
```

### 2. git三大区域

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240929202340880.png" alt="image-20240929202340880" style="zoom:33%;" />



```
- 工作区

    - git init: 初始化git,并把目录里面的文件管理起来

    - 文件名会变红色

    - git add .: 把文件提交到'暂存区'

- 暂存区(缓存区,有后悔药吃)

    - 文件名会变绿色

    - git commit -m '功能描述': 把文件提交到'版本库'

- 版本库

    - 文件最终存放的地方
```



### 3. 短视频功能上线





### 4. 约饭功能





//修复 bug







