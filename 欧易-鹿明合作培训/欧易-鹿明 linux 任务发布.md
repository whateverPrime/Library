# 欧易-鹿明 linux 任务发布

```
更新：20190305 参考答案已存放在路径 /public/hstore5/study/linux/shousiyu 
感谢各位的积极参与

更新：20190617 参考答案一并放在网页上
以便没有集群账号的小伙伴参考
```

[TOC]

> 前置任务及相关软件


```
前置任务：在华为云路径下：/public/hstore2/luming/study/linux
创建各自的工作目录，设置自己的姓名为名称。
每次任务完成情况都会打分的
```

[点击下载notepad]( https://pc.qq.com/detail/0/detail_1300.html)

[点击下载Xshell](https://pc.qq.com/detail/4/detail_2644.html)


## 任务1


**linux 任务1（20180823发布，20180824统一检查）**

>1. 创建目录test1和test2。
>2. 在test1下面创建一个名叫test.txt的文件。
>3. 为test.txt文件增加内容为“I am studying linux.”。
>4. 把test.txt文件拷贝到test2目录下。
>5. 把test1目录移动到test2目录下。
>6. 进入test2目录下的test1目录，删除test.txt文件。
>7. 在第6题的基础上，退出到上一级目录，删除test1目录。


**参考代码**

```
1. mkdir test1 test2
2. touch test1/test.txt
3. echo "I am studying linux.">>test1/test.txt
4. mv test1/test.txt test2/
5. mv test1 test2/
6. cd test2/test1
rm test.txt
7. cd ..
rm -r test1

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


**参考代码**

```
1. touch test2/hw2.sh
2. sed 's/linux/LINUX/g' test.txt >test2.txt
3. sed '1a He is studying linux!' test.txt >test3.txt
4. sed -i '2i You are studying linux!' test3.txt
5. sed -i 's/linux/LINUX/g' test3.txt
6. 自己贴代码咯
```

## 任务3

**20180829发布，20180830检查**

>1. 使用awk 命令将test3.txt 文件中的空格符号换成tab 分隔符
>2. 使用awk+if 语句来做判断，当第一列为'He' 'You' 'I' 的时候分别进行不同处理，详细如下图，结果文件保存为hw3_1.txt
>3. 提取'He' 'You' 'I' 及相关级别 生成文件hw3_2.txt
>4. 将所使用的代码保存在hw3.sh 

**参考代码** 

```
1. 先对test3.txt 文件直接替换空格为tab分隔符
sed -i 's/ /\t/g' test3.txt

2. 利用三个条件匹配加上信息
cat test3.txt |awk -F'\t' -v OFS='\t' '{if($1=="He") print $0";level:bad";else if($1=="You") print $0";level:excellent";else if($1=="I") print $0";python;level:awesome"}' >hw3_1.txt

3. 设置三种分隔符为输入符号，输出分隔符设定为tab分隔符，$NF指的是啥自己查~~
awk -F'\t|;|:' -v OFS="\t" '{print $1,$NF}' hw3_1.txt>hw3_2.txt
```


## 任务4

**20180904发布，20180905检查**
**相关支持文件在路径 /public/hstore2/luming/study/linux/Task_release/task4 下面**


>1. 使用awk输出sutdent.txt中年龄大于等于15的到文件result1.txt
>2. 使用awk输出sutdent.txt中性别为M，且体重小于50的结果到文件result2.txt
>3. 使用awk输出sutdent.txt中ID、Height、Weight三列到文件result3.txt
>4. 使用awk匹配文件sutdent.txt和score.txt，如果学生id存在则将其分数添加到sutdent.txt最后一列，不存在添加NA，输出结果到result4.txt


**参考代码**

```
1. awk -F'\t' '{if($3 >= 15) print $0}' student.txt > result1.txt
2. awk -F'\t' '{if($2 == "M" && $5 < 50) print $0}' student.txt >result2.txt
3. awk -F'\t' '{print $1,$4,$5}' student.txt > result3.txt
4. awk 'NR==FNR{a[$1]=$2} NR!=FNR{if($1 in a){print($0 "\t" a[$1])}else print($0 "\t" "NA")}' score.txt student.txt
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


**参考代码**
```
本次题目要考虑到文件cancer.txt 有重复内容，去重代码 sort -u
1.
who
who |wc -l

2. 交集考虑到两点：1.cancer.txt 有重复内容；2.result1文件表头，可以保留表头放在第一行，也可以直接剔除
sort -u cancer.txt |sort - anti_cancer.txt |uniq -d |grep -v "gene_id" >result1.txt

3. 并集
cat anti_cancer.txt cancer.txt |sort -u |grep -v "gene_id" >result2.txt

4. 取cancer.txt 独有结果,先对cancer.txt 去重生成文件cancer_fixed.txt
sort -u cancer.txt >cancer_fixed.txt
awk -F'\t' -v OFS='\t' 'NR==FNR{a[$1]=$1;next}{if($1==a[$1]) print $1,a[$1];else print $1,""}' result1.txt cancer_fixed.txt |awk -F'\t' -v OFS="\t" '{if($2=="")print $1}' >result3.txt

5. 取anti_cancer.txt 独有结果
awk -F'\t' -v OFS='\t' 'NR==FNR{a[$1]=$1;next}{if($1==a[$1]) print $1,a[$1];else print $1,""}' result1.txt anti_cancer.txt |awk -F'\t' -v OFS="\t" '{if($2=="")print $1}' |grep -v "gene_id" >result4.txt

6. 写个脚本批量匹配
dos2unix result*.txt
for i in $(ls result*.txt) ;
	do
	sed -i "1i gene_id" $i
	n=${i%.txt}
	mkdir $n
	awk -F "\t" 'NR==FNR{a[$1]=$1;b[$1]=$2"\t"$3"\t"$4"\t"$5"\t"$6"\t"$7"\t"$8"\t"$9"\t"$10}NR>FNR{if($1==a[$1]){print $1,b[$1]}else{print $1"\t\t\t\t\t\t\t\t\t"}}' fpkm_anno_test.txt $i >${n}_anno.txt
	mv ${n}_anno.txt $n/
	done

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


**参考代码**
```
1.
df -h
pnodes 10/20 该节点总共20个核心，目前已投递使用10个核心

2.
ln -s /public/hstore2/luming/study/linux/Task_release/task6/linkage.txt ./

3.

chmod -R 744 linkage.txt

4.
wget ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/196/035/GCF_000196035.1_ASM19603v1/GCF_000196035.1_ASM19603v1_genomic.gff.gz

5.
gunzip *.gz

du -sh ./

6. 首先提取 gene 跟 exon 前8列及相关的第9列信息（gene 找关键词 Name, exon 找关键词 Parent）
awk -F'\t' -v OFS='\t' '$3=="gene"||$3=="exon"' GCF_000196035.1_ASM19603v1_genomic.gff |awk -F'\t|;' -v OFS='\t' '$3=="gene"{ {for (f=1; f <= NF; f+=1) {if ($f ~ /Name=/) {print $1,$2,$3,$4,$5,$6,$7,$8,$f}}}}$3=="exon"{ {for (f=1; f <= NF; f+=1) {if ($f ~ /Parent=/) {print $1,$2,$3,$4,$5,$6,$7,$8,$f}}}} ' |sed 's/Name=//g' |sed 's/Parent=//g' >test-gene_tmp.txt

然后根据文件寻找能将 exon 的 Parent 转换成 gene 的 Name 的串起来的信息,请看第三列为mRNA的信息
awk -F'\t' -v OFS='\t' '$3=="transcript"' GCF_000196035.1_ASM19603v1_genomic.gff |awk -F'\t|;' -v OFS='\t' '{print $9,$10}' |sed 's/ID=//g' |sed 's/Parent=//g' >tid2gid.list

再根据 gene 的 ID 去定位 gene 的 Name
awk -F'\t' -v OFS='\t' '$3=="gene"' GCF_000196035.1_ASM19603v1_genomic.gff |awk -F'\t|;' -v OFS='\t' '{print $9,$11}' |sed 's/ID=//g' |sed 's/Name=//g' >gid2gname.list

根据 tid2gid.list 与 gid2gname.list 两文件 得到 exon 的 Parent 的信息最终从 tid 变为 gname
awk -F'\t' -v OFS='\t' 'NR==FNR{a[$1]=$1;b[$1]=$2;next}{if($2==a[$2]) print $1,b[$2];else print $1.""}' gid2gname.list tid2gid.list >t2g.list

最后再根据t2g.list 转化下 test-gene_tmp.gff 中 exon 的 Parent 信息
awk -F'\t' -v OFS='\t' '{print $0}' t2g.list |awk -F'\t' -v OFS='\t' 'NR==FNR{a[$1]=$1;b[$1]=$2;next}{if($9==a[$9]) print $1,$2,$3,$4,$5,$6,$7,$8,b[$9];else print $0}' - test-gene_tmp.gff |awk -F'\t' -v OFS='\t' '{if($3=="gene") print $1,$2,$3,$4,$5,$6,$7,$8,"ID="$9"; Name="$9;else print $1,$2,$3,$4,$5,$6,$7,$8,"Parent="$9}' >test-gene.gff
```


## 任务7

** 20181015发布，20181022检查，作业脚本以task7.sh 命名 **

>1. 在自己的路径task7下创建字母从a到z 为命名的26个文件夹。
>2. 在各自命名的文件夹创建空白的fasta 文件，名字为对应的文件夹名称，如在文件夹a 里创建 a.fasta 
>3. 查看task7下当前路径下的文件夹数量；查看task7路径下包括自路径下所有文件数量
>4. 根据文件file1.txt的第一列和文件file2.txt的第二列匹配，生成file3.txt文件 （相关文件路径/public/hstore2/luming/study/linux/Task_release/task7）
>5. 将file3.txt 文件横竖转置生成file4.txt 文件

**参考代码**
```
1. 第一题跟第二题可以合并起来做
for i in {a..z}
do
	mkdir $i
	touch $i/$i.fasta
done

2. 查看当前路径下的文件夹数量及文件夹路径里面的文件
ls -l|grep "^d"|wc -l
ls -Rl|grep "^-"|wc -l

3. 根据文件信息匹配,需要将两个文件转换为 unix 格式
dos2unix *.txt
awk -F' |\t' 'NR==FNR{a[$2]=$2;next}{if($1==a[$1]) print $0}' file2.txt file1.txt >file3.txt

4. 横竖置换
awk -F'\t' -v OFS='\t' '{for(i=0;++i<=NF;)a[i]=a[i]?a[i] FS $i:$i}END{for(i=0;i++<NF;)print a[i]}' file3.txt >file4.txt
```
## 任务8

** 此次任务以截图为准，打包发我邮件即可 siyu.shou@oebiotech.com **

>1. pnodes 查看节点投递情况
>2. 利用top 查看当前节点正在运行任务情况
>3. 在task8下创建文件夹clean_data 及 genome, 并将/public/hstore2/luming/study/linux/Task_release/task8 下面两个文件夹中对应的文件软链接到自己的路径下
>4. 用qsub 命令提交任务，脚本为 /public/hstore2/luming/study/linux/Task_release/task8/1.2.hisat2_alignment_dUTP.pbs
设置 队列数为1，内核数目2，投递节点为hcu，最大运行时间为1200：00：00小时，任务命名为hisat2
>5. 哪些代码可以查看任务运行情况？ 哪些任务是可以杀掉刚刚提交的任务？ （pnodes 查看后如果节点负载比较高可以杀掉刚刚的任务）

**参考代码**
```
1. pnodes 查看节点投递情况
直接输 pnodes ，一般能查看节点的核心数目及使用的核心数。

2. 利用top 查看当前节点正在运行任务情况
直接输 top ，能看到当前节点下用户正在执行的操作。

#3. 
mkdir clean_data genome
ln -s /public/hstore5/study/linux/Task_release/task8/clean_data/* ./clean_data/
ln -s /public/hstore5/study/linux/Task_release/task8/genome/* ./genome/

#4. 
qsub /public/hstore2/luming/study/linux/Task_release/task8/1.2.hisat2_alignment_dUTP.pbs -N hisat2 -l nodes=1:ppn=2 -q hcu

#5. 
qstat 查看用户投递的队列，队列编号及运行情况，R是运行，Q是排队，C是取消；根据队列编号可以用qdel +队列编号 取消投递的队列任务
```

## 任务9

** 本次任务代码不要写成脚本形式，只需要txt 文件保存在各自的路径下即可；IP地址已做更换，新的路径为：/public/hstore5/luming/study/linux   ** 



>1. 修改个人密码 （只给代码哈）
>2. 判断当前节点 CPU负载 （uptime 命令），需要用一两句文字说明，比如uptime值是多少可以判断为高负载（可以根据pnodes 命令结合来查看）
>3. 统计/usr/lib目录下小于5M并以.txt结尾的文件名到 5m.txt
>4. 把f1.txt文件中每一行的第一个和第二个逗号(,)替换为tab分隔符 生成f2.txt
>5. 只修改 f1.txt 文件 每行最后一个逗号为tab 分隔符 生成f3.txt

**参考代码**
```
1. 修改个人密码 （只给代码哈）
passwd

2. 
uptime 可以查看当前节点负载情况，一般超过当前节点核心数目的2倍为高负载情况。

3. 
find /usr/lib/* -size -5M -type f >./5m.txt

4. 
sed 's/,/\t/;s/,/\t/' f1.txt >f2.txt

5. 
sed 's/\(.*\),/\1\t/' f1.txt >f3.txt
```