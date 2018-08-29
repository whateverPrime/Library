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
