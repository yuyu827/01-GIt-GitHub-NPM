# Git-
GIT基本使用，以及如何链接GITHUB，如果使用NPM命令。

------



## GIT版本控制系统

------

### 版本控制系统：

1. 记录历史版本信息(记录每一次修改的记录)
2. 方便团队相互之间协作开发

### 常用的版本控制系统：

1.  cvs / svn  --> 集中式版本控制系统
2.  git  --> 分布式版本控制系统

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

------

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

------

## NPM

> node package manger : NODE 模块管理工具，根据NPM可以快速安装 卸载所需要的资源文件(Jquery / Vue …)
>
> NODE官网 : https://nodejs.org/zh-cn/   下载NODE(长期支持版)，安装NODE后，NPM也就安装了

```shell
$ node -v
$ npm -v  验证是否安装成功,出现版本号证明安装成功
```

------

## 基于npm进行模块管理

> https://www.npmjs.com/ 基于npm是从nomjs.com平台下载安装

```powershell
$ npm install XXX (要安装的名称)   把模块安装在当前项目中(node_modules)
$ npm install xxx -g  把模块安装在全局环境中
$ npm i xxx@1.0.0     安装指定版本号的模块
$ npm view xxxx versions > xxx.version.json  查看某个模块的版本信息，输出到指定json文件中

/*
*   什么情况下会把模块安装在全局？
*     ->  可以使用"命令"对任何项目进行操作
*     ->  通过 npm root -g  查看全局安装的目录
*     ->  因为在安装目录下生成了 xxx.cmd 的文件 ，所以我们能够使用 xxx  的命令进行操作
*/

/*
*   什么情况下会把模块安装在本地？
*     ->  可以在项目中导入进来使用
*     ->  但是默认不能基于命令来操作(因为没有.cmd文件)
*     ->  但是可以基于 package.json 中的 scripts 配置一些npm可以执行命令，配置后通过 $ npm run xxx 执行
*/

$ npm init -y 初始化当前项目的配置依赖清单(项目文件加的名字不能出现中文 / 大写字母 / 特殊符号)
	==>  创建成功后会在当前项目中生成 package.json 的清单文件
	==>  dependencies : 生产依赖模块(就是安装的插件等模块)
	==>  devDependencies : 开发依赖模块(只有开发的时候需要)
	==>  scripts : 	配置本地可执行命令
	
$ npm i xxx --save 把模块保存在清单生产依赖中
$ npm i xxx --save-dev  把模块保存在清单开发依赖中
$ npm install  跑环境，按照清单安装所需的模块

$ npm uninstall xxxx 卸载
$ npm uninstall xxx -g 卸载安装过的模块
```

------

## 在某个文件夹下执行DOS命令

1. windows + R --> 运行窗口中输入cmd

   == >  磁盘符:进入到指定磁盘

   == >  cd xxx  进入指定目录  ||  cd  直接鼠标拖进想要进入的目录文件

2. 在文件夹地址栏直接输入cmd即可

3. 在文件夹中" shift + 鼠标右键"  ==>  在此处打开命令窗口

4. 如果想查看当前目录中的文件内容 使用  dir 命令

------

## 项目工作流程

------

1. 创建项目文件夹
2. 把他作为一个新的仓库进行代码管理(可以基于$ git clone 把远程仓库克隆下来即可)
3. 初始化模块配置清单package.json  : $ npm init -y
4. 安装所需要的模块: $ npm i jquery bootstrap@3  less ...   
5. 正常开发。
6. 开发中：可能需要在本地配置命令去完成一些功能(LESS文件编译，此时需要配置npm可执行命令)

```json
"scripts" :{
	"less" : "lessc index.less index.css -x",   -x 压缩文件
    "xxx" : "xxx"
}
```

​		需要编译的时候，执行 $ npm run xxx

​		....

​    7.开发中基于 git 把文件进行管理 : 生成对应的历史版本 

​		提交到暂存区  历史区  远程仓库的时候，项目中很多文件是无需处理和提交的

​		例如 : node_modules ||  .idea  || 不需要提交的，生成一个 .gitignore 忽略文件

​		用编辑器生成 .gitignore  添加以下不需要提交项目的名称

```json
# dependencies
node_modules

# testing
/coverage

# production
/build

# misc
.DS_Stroe
.env.local
.env.development.local
.env.test.local
.env.production.local

npm-debug.log*
yarn-debug.log*
yarn-error.log*

# webStorm
.idea
```

​	

​	8. 由于每次提交 .git 的时候， 我们都不去提交 node_modules  , 所以团队协作开发中，我们每当拉下来程序后，都需要 “ 跑环境 ” 执行 $ npm install , 按照项目中的 package.json中的依赖项信息，把缺失的模块都安装一遍。