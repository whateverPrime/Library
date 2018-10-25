# 欧易-鹿明 linux 任务发布

**这是欧易-鹿明 共同学习进步的学习小群，会不断更新有关linux 的作业及相关解释，平均2周一次测试**
[TOC]

##前置任务及相关软件

```
前置任务：在华为云路径下：/public/hstore2/luming/study/linux
创建各自的工作目录，设置自己的姓名为名称。
每次任务完成情况都会打分的
```

[点击下载notepad]( https://pc.qq.com/detail/0/detail_1300.html)

[点击下载Xshell](https://pc.qq.com/detail/4/detail_2644.html)


## 任务1


**linux 任务1（20180823发布，20180824统一检查）**
>1.创建目录test1和test2。
>2.在test1下面创建一个名叫test.txt的文件。
>3.为test.txt文件增加内容为“I am studying linux.”。
>4.把test.txt文件拷贝到test2目录下。
>5.把test1目录移动到test2目录下。
>6.进入test2目录下的test1目录，删除test.txt文件。
>7.在第6题的基础上，退出到上一级目录，删除test1目录。

**任务完成情况**

```
chenmin: 85，但是要注意mv操作，是重命名还是是转移路径
dingshan: 80，但是也要注意mv操作跟cp命令，哪个是拷贝；此外作业脚本最好一键化能跑完的，具体过程不需要写，绝对路径看着也挺多的，相对路径就可以了；最后一个cd 什么情况
tianquan: 你的结果为啥跟chenmin的一样 :D
yinxiaoling: 你的结果为啥也跟chenmin的一样 ：P
wenxing: 100
```

## 任务2

**20180827发布，20180829检查 **


>建议下载notepad（WinScp的使用者可以设置内置编辑器为notepad）
>1. 在test2 里添加一个名为hw2.sh 的文件先放着
>2. 使用sed 替换test 中的'linux' 为'LINUX' 并生成test2文件
>3. 使用sed 在test中新增一行 'He is studying linux!' 并生成test3文件
>4. 使用sed 在test3文件中间直接插入一行 'You are studying linux!' 
>5. 对test3 文件进行直接修改 'linux' 为'LINUX' 
>6. 将以上代码放在hw2.sh 中保存，并用 bash hw.sh 操作实现

**任务完成情况**

```
chenmin: 90 最后忘记直接修改test3.txt 文件
dingshan: 80 根据脚本生成的test3.txt 是空的
tianquan: 80 sed 的命令可以再尝试下，很接近了
yinxiaoling: 90 最后忘记直接修改test3.txt 文件 
lujiawei：100
maHaiChao：80 最后sed 也使用生成重复行了
```

## 任务3

**20180829发布，20180830检查**

>1. 使用awk 命令将test3.txt 文件中的空格符号换成tab 分隔符
>2. 使用awk+if 语句来做判断，当第一列为'He' 'You' 'I' 的时候分别进行不同处理，详细如下图，结果文件保存为hw3_1.txt
>3. 提取'He' 'You' 'I' 及相关级别 生成文件hw3_2.txt
>4. 将所使用的代码保存在hw3.sh 

**hw3_1.txt**
![](http://p5v6ynkbf.bkt.clouddn.com/18-8-29/62444597.jpg)

**hw3_2.txt**
![](http://p5v6ynkbf.bkt.clouddn.com/18-8-29/55437660.jpg)

**对于这次作业感觉棘手的小伙伴不要气馁，因为这是有意设置的。希望大家做到考后100分，逐渐熟练起来，先关代码及相关说明如下（我们这边鼓励大家有不同的方法解决问题）**

```
#先对test3.txt 文件直接替换空格为tab分隔符
sed -i 's/ /\t/g' test3.txt

#利用三个条件匹配加上信息
cat test3.txt |awk -F'\t' -v OFS='\t' '{if($1=="He") print $0";level:bad";else if($1=="You") print $0";level:excellent";else if($1=="I") print $0";python;level:awesome"}' >hw3_1.txt

#设置三种分隔符为输入符号，输出分隔符设定为tab分隔符，$NF指的是啥自己查~~
awk -F'\t|;|:' -v OFS="\t" '{print $1,$NF}' hw3_1.txt>hw3_2.txt
```
**任务完成情况**

```
chenmin: 100
yinxiaoling: 90 i 需要换成大写，进步很大，有了注释
lujiawei： 95 注意第一个level 后面是：号
maHaiChao： 100
tianquan： 70 第一行生成的文件注意下，不要重名，结果出现空的
```

## 任务4

**20180904发布，20180905检查**
**相关支持文件在路径 /public/hstore2/luming/study/linux/Task_release/task4 下面**


>1.使用awk输出sutdent.txt中年龄大于等于15的到文件result1.txt
>2.使用awk输出sutdent.txt中性别为M，且体重小于50的结果到文件result2.txt
>3.使用awk输出sutdent.txt中ID、Height、Weight三列到文件result3.txt
>4.使用awk匹配文件sutdent.txt和score.txt，如果学生id存在则将其分数添加到sutdent.txt最后一列，不存在添加NA，输出结果到result4.txt

**示例如下：**

![](http://p5v6ynkbf.bkt.clouddn.com/18-9-5/58913642.jpg)

**任务完成情况**

```
chenmin: 100
tianquan: 100 最好加上注释哈
yinxiaoling: 80 没有result3.txt 文件
lujiawei:90 只能在自己的路径下运行哈，输入输出不需要用绝对路径
maHaiChao:75 最后一个还没完成
```

## 任务5

** 20180918发布，20180924检查 **
** 相关支持文件路径 /public/hstore2/luming/study/linux/Task_release/task5  **


>1. 查看当前用户并显示用户个数
>2. 取 cancer.txt 与 anti-cancer.txt 交集结果输入到result1.txt
>3. 取 cancer.txt 与 anti-cancer.txt 并集结果输入到result2.txt
>4. 取 cancer.txt 中独有的结果而在 anti-cancer.txt 没有的结果输入到result3.txt
>5. 取 cancer.txt 中没有的结果而在 anti-cancer.txt 独有的结果输入到result4.txt
>6. 写个循环脚本，读取当前路径下的result开头的文件，用各result文件与 fpkm_anno_test.txt匹配ID，匹配到的结果输出到result_anno.txt
如result1.txt 文件与 fpkm_anno_test.txt 匹配后，输出后者含有result1.txt 信息的所有行到result_anno.txt

```
作业完成情况：
```

## 任务6

** 20180930发布，20181010检查，本次任务主要熟悉下常规辅助代码，相关代码放在txt 文件里即可 **
** 相关支持文件路径 /public/hstore2/luming/study/linux/Task_release/task6 **

>1. 查看  linux服务器的文件系统的磁盘空间占用情况；利用pnodes 代码查看各节点情况，适当解释下
>2. 软链接  从支持文件路径下的linkage.txt 文件软链接到自己的task6路径下
>3. 修改自己路径下的linkage.txt 文件权限“所属用户：读写执行；组用户跟其他用户都是只读”
>4. 利用wget 下载linkage.txt 文件到当前路径下
>5. 解压下载文件并查看task6 目录大小
>6. 从解压后的文件提取第三列为gene 及 exon 的信息，要求：前1-8列，第9列要求：
>第三列为gene 提取相关Name 信息; 三列为exon 提取相关Parent 信息,并利用transcript 这行作为中转，修改exon 的Parent 信息讲之与gene 的Name 信息一致，提示如下：

![](http://p5o85qxhq.bkt.clouddn.com/18-9-30/89310848.jpg)

```
作业完成情况：
```


## 任务7

** 20181015发布，20181022检查，作业脚本以task7.sh 命名 **

>1. 在自己的路径task7下创建字母从a到z 为命名的26个文件夹。
>2. 在各自命名的文件夹创建空白的fasta 文件，名字为对应的文件夹名称，如在文件夹a 里创建 a.fasta 
>3. 查看task7下当前路径下的文件夹数量；查看task7路径下包括自路径下所有文件数量
>4. 根据文件file1.txt的第一列和文件file2.txt的第二列匹配，生成file3.txt文件 （相关文件路径/public/hstore2/luming/study/linux/Task_release/task7）
>5. 将file3.txt 文件横竖转置生成file4.txt 文件


## 任务8

** 此次任务以截图为准，打包发我邮件即可 siyu.shou@oebiotech.com **

>1. pnodes 查看节点投递情况
>2. 利用top 查看当前节点正在运行任务情况
>3. 在task8下创建文件夹clean_data 及 genome, 并将/public/hstore2/luming/study/linux/Task_release/task8 下面两个文件夹中对应的文件软链接到自己的路径下
>4. 用qsub 命令提交任务，脚本为 /public/hstore2/luming/study/linux/Task_release/task8/1.2.hisat2_alignment_dUTP.pbs
设置 队列数为1，内核数目2，投递节点为hcu，最大运行时间为1200：00：00小时，任务命名为hisat2
>5. 哪些代码可以查看任务运行情况？ 哪些任务是可以杀掉刚刚提交的任务？ （pnodes 查看后如果节点负载比较高可以杀掉刚刚的任务）