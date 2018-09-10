# 欧易-鹿明 python 任务发布

**这是欧易-鹿明 共同学习进步的学习小群，会不断更新有关python 的作业及相关解释，平均2周一次测试**
[TOC]

##前置任务及相关软件

```
前置任务：在华为云路径下：/public/hstore2/luming/study/python
创建各自的工作目录，设置自己的姓名为名称。
```
**软件Pycharm 及 Anaconda**

[点击下载Pycharm](https://blog.csdn.net/pdcfighting/article/details/80297499)
[点击下载Anaconda](https://www.anaconda.com/download/ )

>建议下载3.6版本的，此外Anaconda 需要设置下环境变量
>环境变量设置：https://jingyan.baidu.com/article/60ccbcebb2b81264cab197b4.html

>如果在华为云上调用python3 的，请在/home/自己个人路径下 添加代码

```
export PATH=/media/data/software/python/Python_v3.6/bin/:$PATH
```
>到以下两个文件中的任意一个

![](http://p5v6ynkbf.bkt.clouddn.com/18-9-10/51690058.jpg)

>如下显示，关掉终端或者source 一下即可用了

![](http://p5v6ynkbf.bkt.clouddn.com/18-9-10/45065569.jpg)



## 数据类型 exercise1 ##

>首先新建一个python脚本： exercise1.py，以下所有题目的实现代码都写入这个脚本里哦。

### 字符串 ###

>Python入门第一步， Hello World！

```
将“Hello World”赋值给变量a，打印输出；
对变量a进行处理，打印输出“hello，world”
提取变量a中的“World”字段
使用交互式函数input，实现用户键入自己的名字，打印输出“hello,xxx”
例：输入Leo，打印出 hello,Leo
```

[input函数使用参考](http://www.runoob.com/python/python-func-input.html)


### 数值运算 ###

>请分别输出

```
-2的绝对值、2的5次方、10除以3的余数、10除以3保留两位小数结果；
用户键入任意两个数x、y，输出这两个数字的乘积 （仍然使用input函数，注意字符串类型与数值类型的转换）
```