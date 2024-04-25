### 语法

```bash
gzip [-acdfhlLnNqrtvV][-S &lt;压缩字尾字符串&gt;][-&lt;压缩效率&gt;][--best/fast][文件...] 或 gzip [-acdfhlLnNqrtvV][-S &lt;压缩字尾字符串&gt;][-&lt;压缩效率&gt;][--best/fast][目录]
```

**参数**：

- `-a`或--ascii 　使用ASCII文字模式。
- `-c`或--stdout或--to-stdout 　把压缩后的文件输出到标准输出设备，不去更动原始文件。
- `-d`或--decompress或----uncompress 　解开压缩文件。
- `-f`或--force 　强行压缩文件。不理会文件名称或硬连接是否存在以及该文件是否为符号连接。
- `-h`或--help 　在线帮助。
- `-l`或--list 　列出压缩文件的相关信息。
- `-L`或--license 　显示版本与版权信息。
- `-n`或--no-name 　压缩文件时，不保存原来的文件名称及时间戳记。
- `-N`或--name 　压缩文件时，保存原来的文件名称及时间戳记。
- `-q`或--quiet 　不显示警告信息。
- `-r`或--recursive 　递归处理，将指定目录下的所有文件及子目录一并处理。
- `-S`<压缩字尾字符串>或----suffix<压缩字尾字符串> 　更改压缩字尾字符串。
- `-t`或--test 　测试压缩文件是否正确无误。
- `-v`或--verbose 　显示指令执行过程。
- `-V`或--version 　显示版本信息。
- `-<压缩效率>` 　压缩效率是一个介于1－9的数值，预设值为"6"，指定愈大的数值，压缩效率就会愈高。
- `--best` 　此参数的效果和指定"-9"参数相同。
- `--fast` 　此参数的效果和指定"-1"参数相同。

### 实例

压缩文件

```bash
[root@runoob.com a]# ls //显示当前目录文件
a.c b.h d.cpp
[root@runoob.com a]# gzip * //压缩目录下的所有文件
[root@runoob.com a]# ls //显示当前目录文件
a.c.gz    b.h.gz    d.cpp.gz
[root@runoob.com a]# 
```

接范例1， 列出详细的信息

```bash
[root@runoob.com a]# gzip -dv * //解压文件，并列出详细信息
a.c.gz:     0.0% -- replaced with a.c
b.h.gz:     0.0% -- replaced with b.h
d.cpp.gz:     0.0% -- replaced with d.cpp
[root@runoob.com a]# 
```

接范例1，显示压缩文件的信息

```bash
[root@runoob.com a]# gzip -l *
     compressed    uncompressed ratio uncompressed_name
         24          0  0.0% a.c
         24          0  0.0% b.h
         26          0  0.0% d.cpp
```