

## GIT版本控制系统

------

### 版本控制系统：

1. 记录历史版本信息(记录每一次修改的记录)
2. 方便团队相互之间协作开发

### 常用的版本控制系统：

1.  cvs / svn  --> 集中式版本控制系统
2. git  --> 分布式版本控制系统

------

## GIT工作原理 

- 工作区：能看到的，并且用来写代码的的区域
- 暂存区：临时存储用的
- 历史区：生成历史版本

工作区 --> 暂存区 --> 历史区

------

## 1. GIT全局配置

> 第一次安装完成git后，在全局环境下查看配置信息

```shell
$ git config -l 	查看配置信息
$ git config --global -l  查看全局配置信息 

配置全局信息:用户名和邮箱
$ git config --global user.name 'xxx'  配置用户名字
$ git config --global user.email 'xxx@xx.xx'  配置邮箱
```

------

## 2.创建仓库完成版本控制

> 创建本地git仓库

```shell
$ git init
// ==> 会生成一个隐藏文件夹 ".git"(这个文件夹千万不要删，因为暂存区和历史区还有一些其他的信息都在这里，删除后就不是一个完成的仓库)
```

![image-20200411181832527](C:\Users\26077\AppData\Roaming\Typora\typora-user-images\image-20200411181832527.png)

> 在本地编写完成后(在工作区)，把一些文件提交到暂存区

```shell
$ git add xxx	把某一个文件或者文件夹提交到暂存区
$ git add .   把当前仓库(文件夹)中所有最新修改的文件都提交到暂存区
$ git add -A     把当前仓库(文件夹)中所有最新修改的文件都提交到暂存区

$ git status   查看当前文件的状态(红色代表在工作区，绿色代表在暂存区，看不见东西证明所有修改的信息都已提交到历史区)
```

![image-20200411183645659](C:\Users\26077\AppData\Roaming\Typora\typora-user-images\image-20200411183645659.png)

![image-20200411183610593](C:\Users\26077\AppData\Roaming\Typora\typora-user-images\image-20200411183610593.png)

> 把暂存区内容提交到历史区

```shell
$ git commit -m'描述信息：本次提交内容的一个描述'	-m不加空格写描述信

查看历史版本信息(历史记录)
$ git log  
$ git reflog  包含回滚信息
```

> 历史记录回滚

```shell
$ git reset --hard  版本号		
```

<img src="C:\Users\26077\AppData\Roaming\Typora\typora-user-images\image-20200413090026773.png" alt="image-20200413090026773" style="zoom:150%;" />