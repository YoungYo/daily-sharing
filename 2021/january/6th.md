# 6th
#### 一

一次性替换多个文件中的指定字符串

假设有三个文本文件，file1.txt，file2.txt，file3.txt，我想把这三个文本文件中的「good」替换成「nice」，可以用这个命令：

sed -i '.bak' 's/good/nice/g' file1.txt file2.txt file3.txt

其中，「'.bak'」是指定备份文件的后缀名，为了防止误操作，sed 要求修改文件内容时要备份，如果不想备份，可以用空字符串代替「'.bak'」，即：

sed -i '' 's/good/nice/g' file1.txt file2.txt file3.txt

s 前面可以指定行号，从而实现对文件局部的修改。比如「2,8s/good/nice/g」就是只把第 2 行到第 8 行的 good 替换成 nice。还有另外几种方式指定行号，见图一。如果把最后面那个「g」去掉，就只会替换每行中第一次出现的 good。

其实 s 命令是匹配正则表达式并替换，所以可以用「s/a\db/nice」将匹配到「a\db」的字符串都替换成 nice。

最后的文件列表，也可以用通配符匹配，比如把「file1.txt file2.txt file3.txt」改成「 *.txt」，就是替换所有以「.txt」结尾的文件中的内容。

<img src="https://tva1.sinaimg.cn/large/008eGmZEly1gnbbh5q9yyj30ml0h6q6k.jpg" alt="3891609910671_.pic_hd" style="zoom:50%;" />

**参考资料：**

- 《The Linux Command Line Fifth Internet Edition》第 20 章 - Text Processing - Editing on the Fly - sed

#### 二

如图一所示，反向器的输出也是它的输入，这种电路我们称之为振荡器。由于从输出到输入有一定的时间间隔，所以振荡器输出端的输出信号呈周期性变化，即一会儿输出电压，一会儿不输出电压，也可以说是要么输出 0，要么输出 1，其输出序列如图二所示。有了振荡器，就可以实现电路的自动开关，从而使计算机自发地工作。因为随着时间的变化，振荡器的输出在 0 和 1 之间周期性变化，所以振荡器也被称为始终，这个变化的周期叫做时钟周期，周期的倒数就是振荡器的频率，也就是我们常说的主频。

所以为什么提高主频会使计算机运行速度变快，就是因为主频决定了计算机执行指令的频率，主频越大，单位时间内计算机执行的指令就越多，响应速度也就变快了。同样地，提高主频导致计算机功耗增大也是因为这个。

![振荡器](https://tva1.sinaimg.cn/large/008eGmZEly1gnbbgpjrapj30c903xjra.jpg)

![振荡器输出序列](振荡器输出序列.png)

**参考资料：**

- 《编码：隐匿在计算机软硬件背后的语言》——第 14 章

