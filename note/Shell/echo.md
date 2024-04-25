
### 1.显示普通字符串:
```bash
echo "It is a test"
```



### 2.显示转义字符
```bash
echo "\"It is a test\""
```



### 3.显示变量

read 命令从标准输入中读取一行,并把输入行的每个字段的值指定给 shell 变量
```bash
#!/bin/sh
read name 
echo "$name It is a test"
```



### 4.显示换行
```bash
echo -e "OK! \n" # -e 开启转义
echo "It is a test"
```



### 5.显示不换行
```bash
#!/bin/sh
echo -e "OK! \c" # -e 开启转义 \c 不换行
echo "It is a test"
```


### 6.显示结果定向至文件
```bash
echo "It is a test" > myfile
echo "sda">> myfile
#结果追加到myfile文件
```


### 7.原样输出字符串，不进行转义或取变量(用单引号)
```bash
echo '$name\"'
```


### 8.显示命令执行结果
```bash
 echo `date '+%T'`
```


**注意：** 这里使用的是反引号 `, 而不是单引号 '。

### 9.用法
```bash
echo $PATH
#显示环境变量
```
