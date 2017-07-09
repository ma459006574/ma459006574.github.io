---
layout: post
title:  "KettleEasyExpand"
date:   2017-07-09 12:29:12 +0800
categories: jekyll update
---
# 插件简介

一个简化kettle插件开发的通用插件，采用JSON作为参数配置，省去ui调试设计步骤，只需一个类就可以开发一个插件。基于本插件开发的插件将很容易集成到[kettle管理平台](https://github.com/majinju/kettle-manager)中去。

## 设计初衷

 该kettle插件功能类似kettle现有的定义java类插件，自定java类插件主要是支持在kettle中直接编写java代码实现自定特殊功能，而本控件主要是将自定义代码转移到jar包，就是说自定义功能的实现改为在eclipse等ide中开发。

 设计本插件的原因是直接在kettle中写java代码是很不容易的事，开发体验与eclipse差得远，java语法还要受到限制，调试麻烦。实现点简单的逻辑还行，稍微复杂一点就比较麻烦，需要对java和kettle相关接口很熟悉。而简单的功能可以采用javascript脚本实现，复杂的功能一般人很难直接在自定义java类控件中编写java实现。

 有人说可以每次直接开发新插件，虽然说java的插件机制还是很不错的，但开发一个插件还是没那么容易的，需要设计元数据，插件件功能实现，插件操作界面设计等，其中操作界面的调整是我最不愿意花时间的，慢慢调我也能调出常见控件的配置界面，但我觉得没必要，所以要实现一个完善的插件需要做的事情还是很多的。

 而本插件综合了以上两种机制，既有自定义java类的简单性，直接编写核心业务代码，操作界面统一使用一个JSON对象作为参数设置途径，所以基于此开发功能，只需继承一个基类而编写一个功能实现类就可以了；又有直接开发插件的便捷性，只需将相关的jar包作为用户类库导入项目，创建一个类，继承基类，就可以在eclipse中尽情的编写你的业务代码了。

## 关键信息

1.	[项目博客地址](http://blog.benma666.cn/)
2.	[项目源码地址](https://github.com/majinju/KettleEasyExpand)
3.	问题反馈邮箱：jinjuma@yeah.net。

# 插件部署



# 插件开发

## 环境搭建

1. 在eclipse中创建用户类库ku，到[kettle管理平台项目](https://github.com/majinju/kettle-manager)介绍的博文中下载0.2.0版部署包，然后将部署包的lib目录中的jar全部加入。
1. 在eclipse中创建用户类库kettleLib，将你的kettle的目录下的lib全部加入。
1. 在eclipse中创建一个java项目，添加前面创建的两个用户类库到构建路径。
1. 然后就可以新建一个java类，按后面的步骤进行插件开发了。

## 作业插件开发

[示例代码](https://github.com/majinju/KettleUtil/blob/master/src/main/java/cn/benma666/kettleutil/utilrun/JeurDemo.java)

![image](http://blog.benma666.cn/project/KettleUtil/images/v1.0.0/作业插件示例.jpg)

## 转换插件开发

[示例代码](https://github.com/majinju/KettleUtil/blob/master/src/main/java/cn/benma666/kettleutil/utilrun/KurDemo.java)

![image](http://blog.benma666.cn/project/KettleUtil/images/v1.0.0/转换插件示例.jpg)

# 插件调试

1. [kettle源码运行讲解](http://www.cnblogs.com/majinju/p/4455107.html)
1. [kettle源码工程](https://github.com/majinju/pentaho-kettle)