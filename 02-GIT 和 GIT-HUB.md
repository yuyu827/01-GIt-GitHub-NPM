## GIT 和 GIT-HUB

> GIT-HUB: https://github.com
>
> 一个开源的源代码管理平台，可以在自己账户下创建仓库，用来管理项目的源代码(源代码是基于git传到仓库中)
>
> (JQuery Vue Reacat)
>
> 所熟知的插件 类库 框架 等都在这个平台上有托管，可以下载观看和研究源码



<img src="C:\Users\26077\AppData\Roaming\Typora\typora-user-images\image-20200413093130621.png" alt="image-20200413093130621" style="zoom:50%;" />

## 1.Settings 设置基本信息

- Profile  修改自己的基本信息
- Account  账户信息
- Security  修改密码

------

## 2. New repository  创建仓库

new repository --> 填写信息 --> Create respository

- public 公共仓库作为开源项目
- private  私有仓库作为内部团队协作管理的项目

Settings -->  删除仓库 Delete this respository

Code 可以查看历史版本信息和分支信息

------

## 3.把本地仓库信息提交到远程仓库

```shell
// => 建立本地仓库和远程仓库的链接

查看本地仓库和哪些远程仓库保持连接
$ git remote -v  查看所有链接

让本地仓库和远程仓库新建一个链接 origing是随便起的链接名(可以改成自己想要的，一半都使用这个)
$ git remote add origin [GIT远程仓库地址]

移除关联信息
$ git remote rm origin

```

<img src="C:\Users\26077\AppData\Roaming\Typora\typora-user-images\image-20200413102129045.png" alt="image-20200413102129045" style="zoom:150%;" />

```shell
提交之前最好先拉取
$ git pull origin master
$ git pull --rebase origin master  

把本地代码提交到远程仓库(需要输入github的用户名和密码)
$ git push origin master
$ git push -u origin master
```

------

真实项目使用clone

```shell
$ git clone [远程仓库git地址] [别名：可以不设置，默认是仓库名]
/*
	真实项目开发流程
	1.组长或者负责人先创建中央仓库(增加协作者，添加组员)
	2.小组成员基于 $ git clone 把远程仓库及默认的内容克隆到本地一份
		(解决了三件事情:
			a.初始化一个本地仓库"git init"
			b.和对应的远程仓库保持了关联"git remote add"
			c.把远程仓库默认内容拉取到本地"git pull master"
		)
	3.每个组员完成自己的代码后，把修改内容存放到历史区
		a.git add  把工作区文件上传到暂存区
		b.git commit -m"描述信息" 把文件存放到历史区
		c.git pull / git push 把本地信息和远程仓库信息保持同步即可(可能涉及冲突的处理)
*/
```

