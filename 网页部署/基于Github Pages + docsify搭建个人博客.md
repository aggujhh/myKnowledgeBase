## 准备工作

#### 1、要有git环境，有github账号

因为我们要使用Github Pages来部署我们的应用，请先注册下github的账号，官网：[Github](https://github.com/)

#### 2、有node环境

docsify框架需要有node环境的支持。上node.js的官网下载安装包，此处下载Windows版本的，点下一步一路安装下去即可。另外需要配置下环境变量。



## 使用docsify命令生成文档站点

#### 安装docsify-cli 工具

推荐安装 docsify-cli 工具，可以方便创建及本地预览文档网站。

```bash
npm install -g docsify-cli 
```

因为我们已经安装了node环境，所以直接打开CMD窗口执行上面的命令就好了。

#### 初始化一个项目

然后我们选择一个根目录,  打开CMD，cd到该目录，执行如下命令：

```bash
docsify init 
```

执行完成后，根目录下会生成几个文件。

- index.html 入口文件
- README.md 会做为主页内容渲染
- .nojekyll 用于阻止 GitHub Pages 会忽略掉下划线开头的文件



#### 启动项目，预览效果

到这里，就可以启动项目，然后看下效果了。

使用下面命令启动项目：

```bash
docsify serve docs
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105134816523.png)

浏览器输入：[http://localhost:3000](http://localhost:3000/)

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020010513494279.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

看着有点简陋，不过框架已经搭好了，接下来就是一些配置了。

#### 增加一些配置，变身成真正的blogsite

这里我们主要配置一下封面、左侧导航栏和首页，其他的配置可以参考docsify官网。

**1、配置左侧导航栏**

在根目录下新建一个`_sidebar.md` 的md文件，内容如下：

```bash
- 设计模式

  - [第一章节](desgin-pattern/Java面试必备：手写单例模式.md)
  - [工厂模式](desgin-pattern/工厂模式超详解（代码示例）.md)
  - [原型模式](desgin-pattern/设计模式之原型模式.md)
  - [代理模式](desgin-pattern/设计模式之代理模式.md)

- Spring框架

  - [初识spring框架](spring/【10分钟学Spring】：（一）初识Spring框架.md)
  - [依赖注入及示例](spring/【10分钟学Spring】：（二）一文搞懂spring依赖注入（DI）.md)
  - [spring的条件化装配](spring/【10分钟学Spring】：（三）你了解spring的高级装配吗_条件化装配bean.md)

- 数据库
```

这其实就是最基本的md文件，里面写了一些链接而已。

只有上面的`_sidebar.md` 文件是不行滴，还需要在index.html文件中配置一下。在内嵌的js脚本中加上下面这句：

```bash
loadSidebar: true
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105141053778.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

好了，我们来看下效果。

注意，无需我们重新启动docsify serve，保存刚才添加和修改的文件就行。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105141312381.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

**2、配置个封面**

套路和上面配置左侧导航栏是一样的。

首先新建一个 `_coverpage.md` 的md文件，这里面的内容就是你封面的内容。

```bash
# Myblogs


> 我要开始装逼了


[CSDN](https://blog.csdn.net/m0_37965018)
[滚动鼠标](#introduction)
```

然后在index.xml文件中修改js脚本配置，添加一句：

```bash
coverpage: true
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105141937426.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

看下效果

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105142017986.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

**3、配置一个首页**

最后我们来配置下首页，也就是封面完了之后，第一个看到的界面。

其实就是根目录下`README.md` 文件的内容。

我们一直没有管他，默认就是这个样子的：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105142433933.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

改一下，放上自己牛逼的经历或者是标签。

```bash
# 最迷人的二营长

> [个人博客](https://blog.csdn.net/m0_37965018)


> [GitHub](https://github.com/Corefo/ "github")
```

看下效果

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105142733890.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)



## 部署到Github上

没有域名 + 服务器怎么办，不用担心，我们有Github啊，通过Github Pages的功能，我们可以将个人站点托管到github上。

#### 登录github账号，创建仓库

登录github的官网，创建一个仓库，起个名字吧，就叫myblogs。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105143404136.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

仓库创建好了，利用GitHub Desktop同步本地仓库。

![image-20240111164947408](C:\Users\cheny\AppData\Roaming\Typora\typora-user-images\image-20240111164947408.png)



#### 使用Github Pages功能建立站点

这一步相当简单，简单到令人发指！！

在myblogs仓库下，选中 `Settings` 选项里的`Pages` 页签设置`Source` 和`branch`

![image-20240111165157460](C:\Users\cheny\AppData\Roaming\Typora\typora-user-images\image-20240111165157460.png)



![image-20240111165451202](C:\Users\cheny\AppData\Roaming\Typora\typora-user-images\image-20240111165451202.png)

好了。

同时，还会提示你在哪里去访问你的站点。

按照提示，我们访问看看：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200105145852248.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L20wXzM3OTY1MDE4,size_16,color_FFFFFF,t_70)

