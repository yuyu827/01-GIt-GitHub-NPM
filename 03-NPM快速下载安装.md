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

