# 欧易-鹿明 python 任务发布 #

**这是欧易-鹿明 共同学习进步的学习小群，会不断更新有关python 的作业及相关解释，平均2周一次测试**
[TOC]

## 前置任务及相关软件 ##

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

**任务完成情况**

```
chenmin: 95 前面完成的很好~~最后一题的int只能转换为整数，小数无法运算，可用eval将字符串转换为表达式
yinxiaoling: 79 作为第一个提交作业的童鞋，积极性很赞~~ 需要注意：1）insert是对列表的处理方法，对字符串不适用。逗号替换可以使用replace。2）a[1] 只提取了a中的第二个字母 3）print("hello," + c +) 手抖多了个加号嘛? 4）-2的绝对值：abs(-2) 5）10除以3保留两位小数：round(10/3,2) 6）字符串类型转换为表达式：eval 7）代码中没有循环或判断时，不需要tab缩进，直接写就好。
tianquan: 95 只差一点~~第四题代码少了半个括号
lujiawei： 95 第2题注意题目是对变量a进行处理，不是直接打印出来，参考replace方法。
wangyayu：95 最后一题int()只能转换为整数，小数无法运算，可用eval()。
mahaichao: 100 
```

## 数据类型 exercise2 ##

> 本次练习的数据类型是**列表**和**字典**

### 列表 ###

>1. 创建一个名为```num```的列表，其中包含1，2，3，4，5 这五个元素；

>2. 将列表`num`中的元素 1 替换为 a；

>3. 删除```num```中的元素 5 ；

> 4. 在列表```num```的末尾再添加两个元素：a，b；

> 5. 在列表```num```的元素 3 后面，添加元素 a；

> 6. 请反向输出列表```num```；

>7. 输出列表```num```的长度；

> 8.  统计输出列表```num```中 a 出现的次数


### 字典 ###

> 9. 已知有两个列表```list1```：1，2，3，```list2```：a，b，c，请将它们转换生成字典```d```  {1: 'a', 2: 'b', 3: 'c'}

> 10. 请在字典d中添加一个键值对， 4: 'd'

> 11. 输出字典中键 2 的对应值；

> 12. 使用for循环遍历字典```d```，打印出所有键和值

**任务完成情况**

```
lujiawei：99 腻害哦~~ 统计a出现次数稍有点麻烦了，直接使用count方法即可。
tianquan： 99 腻害+1~~ 一样，统计次数稍麻烦了，直接使用count方法即可。
wangyayu： 100 棒棒哒！
yinxiaoling： 70  1）计数的问题：python从零开始计数，因此元素1在列表第1位num[0]，元素5为num[4]，num.insert(3,'a')
                  2）添加键值对时程序报错的原因是生成字典的方法有误，而且少了半个括号，参考：dict(zip(list1,list2))
				  3）遍历字典试试d.items
chenmin： 100   尝试用两种方法解题，还有自己的思考~~简直是优等生的典范嘛
                问题1）列表中的元素加引号和不加引号有什么区别：加引号的均表示为字符串类型，如果是数值可以不加引号，加了则变为字符串类型了。如果是字符串则必须加引号，除非在前面已经赋值给某变量。可以使用type()来查看元素的类型，如type(num[0])。
			    问题2）将两个列表转换成字典，dict zip 方法：正确写法是dict(zip(list1,list2))，两个list间以逗号相隔，dict已经是创建字典的函数，外面无需再加｛｝。
shousiyu： 100 寿老师，不多说了~
mahaichao: 100 做的很好~也有两种方法解答，下次争取早点交哈
```

##  Exercise3 ##

> 本周主要练习的是 **if判断** 和 **循环语句**

### if判断 ###

>1.  用户输入两个数，比较大小，输出较大的数。若相等，则输出其中一个；

>2.  使用 if判断 编写一段代码：用户输入一个分数 （input函数），90分以上（含）成绩为A，80（含）~90为B，60（含）~80为C，60以下为D，判断该分数所属的成绩区域。

>3.  思考：输入三个数比较大小，从小到大输出，如何实现？


### 循环 ###

>4. 使用while 循环，输出从0 到10的整数；

> 5. 仍然输出从0 到10的整数，请使用for 循环range函数实现；

> 6. 输出1~100内的所有奇数，并求和；

> 7. 输出1~100内所有奇数的平均值；

> 8. 使用while，输出1，2，3，4，6，7，8，9；

> 9. 字符串s=“abcdeabcdabcaba”，输出字符串s中出现频率最高的字符

** 作业完成情况 **

```
lujiawei： 80  4/5题是从0开始，while循环i = 0，for循环range(0, 11)

tianquan： 75  第三题思路可以，最好把它用代码写出来，4/5题同上，从0开始：while循环i = 0，for循环range(0, 11)

chenmin： 70 问题1）为什么number1和number2不需要做eval转化也可以执行?
                  input默认返回的是字符串类型，字符串间也可以比大小（按ASCII码比），所以不用eval转化也能得到结果。（试试看数字和字母比是什么结果？）
               2）第二题elif已有否定上一层判断的意思，不需要再判断and score <... 
               3）第三题pycharm上是可以运行的，6/7题结果有问题，else:pass没有缩进，且不需要加。
               4）第九题方法有很多，可以用字典形式，将每个字符和出现的次数生成一个字典，获得次数最多对应的key；也可以参考wangyayu、tianquan或lujiawei的方法

yinxiaoling： 68 1）第二题if 后面不需要加括号哈，elif也不用再判断c <...
                 2）第三题可以把想的用代码写出来
                 3）第七题average变量名前后不一样，所以出不了结果
                 4）最后一题方法很多，可以用字典形式，将每个字符和出现的次数生成一个字典，获得次数最多对应的key；也可以参考wangyayu、tianquan或lujiawei的方法

wangyayu： 90 1）第二题elif已有否定上一层判断的意思，不用再判断a <... 
              2）第三题是可以的，把int改成eval更好，否则无法执行小数的判断
              3）第五题for循环range（0,11）
              PS：最后一题方法很棒~

```

##  Exercise4 ##

> 文本处理 & 正则表达式

### 文本处理 ###

>1.   请读取 test1.txt，打印输出文本内容；

>2.   请去除文本中的空行，然后输出该文本的总行数；

>3.   请将文本中的 “python”  改为 “linux”，写入新文件new.txt； 

> 4.  请读取  test2.txt，将文件中所有mRNA对应的基因序列号存入mRNA.txt，lncRNA对应序列号存入lncRNA.txt。



### 正则表达式 ###

> 5. 请使用re 模块，实现：随机输入一行字符，分别统计其中的数字、字母、空格和其他字符出现的个数；

> 6. 假设有一串字符 "date:2018-09-25 email:a123@oebiotech.com phone:021-12345678 tel:123456789 website:www.oebiotech.com ip:192.168.10.129 email:b123@oebiotech.com email:c123@lumingbio.com email:d123@lumingbio.com"
>
>    请使用**re模块**分别匹配得到 日期date、phone、tel、website、ip及所有email信息。
