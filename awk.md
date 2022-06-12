### awk

awk是一个强大的Linux命令，有强大的文本格式化能力，好比将一些文本数据格式化成专业的excel表的样式

awk早期在Unix上实现，用的awk是gawk,是GNU awk的意思

which awk 

ll /usr/bin/awk    



awk更是一门编程语言，支持条件判断、数组、循环等功能



#### 三剑客的特点

- grep , 擅长单纯的查找或匹配文本内容
- awk，  更适合编辑，处理匹配到的文本内容
- sed,  更适合格式化文本内容，对文本进行复杂处理



### awk基础

awk语法

```
	awk [option] 'pattern[action]' file...
	
	awk 参数 '条件动作' 文件
	
```

![1655051484425](C:\Users\12874\AppData\Roaming\Typora\typora-user-images\1655051484425.png)

Action指的是动作，awk擅长文本格式化，且输出格式化后的结果，因此最常用的动作就是 `print` 和 `printf`



#### awk内置变量

| 内置变量              | 解释                              |
| --------------------- | --------------------------------- |
| $n                    | 指定分隔符后，当前记录的第n个字段 |
| $0                    | 完整的输入记录                    |
| FS                    | 字段分隔符，默认空格              |
| NF(number of fields)  | 分割后，当前行一共多少个字段      |
| NR(number of records) | 当前记录数                        |
| 更多变量man 查手册    | man awk                           |



#### awk案列

```
demo
awk '{print $1}' luffy.txt    #以空格为分割
	$0 表示一整行
	$1 表示第一列
	$2 表示第二列
	$NF 当前分割后最后一列
	$(NF-1) 倒数第二列

#一次性输出多列信息
	awk '{print $1,$2}' luffy.txt

#自动定义输出内容
awk，必须 外层单引号 ， 内层双引号 
内置变量 $1、$2都不得添加双引号，否则会被识别为文本，尽量别加引号
	awk '{print "第一列:"$1,"第一列:"$2}' luffy.txt
	



```

