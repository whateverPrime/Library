# 欧易-鹿明 linux 任务发布

**这是欧易-鹿明 共同学习进步的学习小群，会不断更新有关linux 的作业及相关解释，平均2周一次测试**
[TOC]

##前置任务及相关软件##

```
前置任务：在华为云路径下：/public/hstore2/luming/study/linux
创建各自的工作目录，设置自己的姓名为名称。
```

[点击下载notepad]( https://pc.qq.com/detail/0/detail_1300.html)

[点击下载Xshell](https://pc.qq.com/detail/4/detail_2644.html)


## 任务1##

**正式开始啦~~下次测试时间20180903 **
```
linux 任务1（20180823发布，20180824统一检查）
1.创建目录test1和test2。
2.在test1下面创建一个名叫test.txt的文件。
3.为test.txt文件增加内容为“I am studying linux.”。
4.把test.txt文件拷贝到test2目录下。
5.把test1目录移动到test2目录下。
6.进入test2目录下的test1目录，删除test.txt文件。
7.在第6题的基础上，退出到上一级目录，删除test1目录。
```

##任务2##

**20180827发布，20180829检查 **

```
建议下载notepad（WinScp的使用者可以设置内置编辑器为notepad）
1. 在test2 里添加一个名为hw2.sh 的文件先放着
2. 使用sed 替换test 中的'linux' 为'LINUX' 并生成test2文件
3. 使用sed 在test中新增一行 'He is studying linux!' 并生成test3文件
4. 使用sed 在test3文件中间直接插入一行 'You are studying linux!' 
5. 对test3 文件进行直接修改 'linux' 为'LINUX' 
6. 将以上代码放在hw2.sh 中保存，并用 bash hw.sh 操作实现
```

##任务3##

**20180829发布，20180830检查**

```
1. 使用awk 命令将test3.txt 文件中的空格符号换成tab 分隔符
2. 使用awk+if 语句来做判断，当第一列为'He' 'You' 'I' 的时候分别进行不同处理，详细如下图，结果文件保存为hw3_1.txt
3. 提取'He' 'You' 'I' 及相关级别 生成文件hw3_2.txt
4. 将所使用的代码保存在hw3.sh 
```
**hw3_1.txt**
![](http://p5v6ynkbf.bkt.clouddn.com/18-8-29/62444597.jpg)

**hw3_2.txt**
![](http://p5v6ynkbf.bkt.clouddn.com/18-8-29/55437660.jpg)

**对于这次作业感觉棘手的小伙伴不要气馁，因为这是寿老师我故意刁难你们的！！！，除非是有基础，要不然一下子接触很少会知道的，但是希望大家做到考后100分，就是之前不知道的知识点这次能渐渐熟练起来，代码及相关说明如下（你有更好的方法也可以展示出来）**
```
#先对test3.txt 文件直接替换空格为tab分隔符
sed -i 's/ /\t/g' test3.txt

#利用三个条件匹配加上信息
cat test3.txt |awk -F'\t' -v OFS='\t' '{if($1=="He") print $0";level:bad";else if($1=="You") print $0";level:excellent";else if($1=="I") print $0";python;level:awesome"}' >hw3_1.txt

#设置三种分隔符为输入符号，输出分隔符设定为tab分隔符，$NF指的是啥自己查~~
awk -F'\t|;|:' -v OFS="\t" '{print $1,$NF}' hw3_1.txt>hw3_2.txt
```

##任务4##

**20180904发布，20180905检查**
**相关支持文件在路径 /public/hstore2/luming/study/linux/Task_release/task4 下面**

```
1.使用awk输出sutdent.txt中年龄大于等于15的到文件result1.txt
2.使用awk输出sutdent.txt中性别为M，且体重小于50的结果到文件result2.txt
3.使用awk输出sutdent.txt中ID、Height、Weight三列到文件result3.txt
4.使用awk匹配文件sutdent.txt和score.txt，如果学生id存在则将其分数添加到sutdent.txt最后一列，不存在添加NA
```
**示例如下：**

![](http://p5v6ynkbf.bkt.clouddn.com/18-9-5/58913642.jpg)



