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

### 3. 回滚

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240929205222634.png" alt="image-20240929205222634" style="zoom:33%;" />

```c
 git reset --hard c965bd2ea37e1eda0178643505fa10d3cf29f998(git log查看版本号)
 //如果需要跳回到后来的版本用git reflog查看,然后执行回滚操作
 //上图执行git checkout -- 文件名.c    
```

### 4. 分支

如下图描述，现在设计了一款软件，C1为第一版，C2为第二版。其中，C1中的文件有a、b、c。那么假设C2较之前的C1版本的区别只是改动了a文件为a’。那么git的生成C2的逻辑就只是把a‘保存了。而C2中的b、c选择指针的方式指向C1中的b、c文件【类似快照的感觉】。这种做法可以很大程度节约存储成本。

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240930154443308.png" alt="image-20240930154443308" style="zoom: 33%;" />

如果新出了第3版C3【在C2基础上改动】，那么其思路也是类似的，只是保存了C2中改动的部分，没改动的一律以指向的形式【类似快照】

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240930154758261.png" alt="image-20240930154758261" style="zoom: 50%;" />

​      1）分支。如下图分支1，这里假设C3版本之后，分别有C4和C5【也就是说C4和C5是同样是基于C3的】。二者因为要新增的功能不同，因此分开了两个支线，当最后完成后，进行整合为C6【这里是简单介绍下分支。】

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240930154918679.png" alt="image-20240930154918679" style="zoom: 33%;" />

 2）紧急修复线上bug的思路。这里假设我们基于C3版本新增功能为C4版本时【还在开发中，阶段为C4_1如下图的1个月】，突然C3版本出现bug，我们不可能舍弃新开发的C4_1去退回C3版本，因此我们可以利用分支思想，来新增C5版本来修复bug

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240930155745721.png" alt="image-20240930155745721" style="zoom: 50%;" />



 3)分支后合并。当修复好bug生成版本C5后，我们需要生成版本C6来将C5合并到主线上面；同理，新增的版本C4_2已经将新增功能写好时，就可以合并到C7了。【所谓主线，即术语master。就是C1、C2、C3、C6、C7。而类似于C4和C5的分支，则可以自己命名，比如C5为修bug的分支，C4为开发分支dev】。这里不难看出，分支起到了隔离环境的作用。如下图示。

![image-20240930160056570](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240930160056570.png)



### 5. 分支操作





```c
//查看分支
git branch
    
//创建分支
git branch 分支名称    


//切换分支
git checkout 分支名称    






```



//商城开发了50%

//继续开发完毕

















