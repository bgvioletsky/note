### 语法

```
grep [options] pattern [files]
或
grep [-abcEFGhHilLnqrsvVwxy][-A<显示行数>][-B<显示列数>][-C<显示列数>][-d<进行动作>][-e<范本样式>][-f<范本文件>][--help][范本样式][文件或目录...]
```

- pattern - 表示要查找的字符串或正则表达式。
- files - 表示要查找的文件名，可以同时查找多个文件，如果省略 files 参数，则默认从标准输入中读取数据。

**常用选项：**：

- `-i`：忽略大小写进行匹配。
- `-v`：反向查找，只打印不匹配的行。
- `-n`：显示匹配行的行号。
- `-r`：递归查找子目录中的文件。
- `-l`：只打印匹配的文件名。
- `-c`：只打印匹配的行数。

**更多参数说明**：

- **`-a` 或 --text** : 不要忽略二进制的数据。
- **`-A`<显示行数> 或 --after-context=<显示行数>** : 除了显示符合范本样式的那一列之外，并显示该行之后的内容。
- **`-b` 或 --byte-offset** : 在显示符合样式的那一行之前，标示出该行第一个字符的编号。
- **`-B`<显示行数> 或 --before-context=<显示行数>** : 除了显示符合样式的那一行之外，并显示该行之前的内容。
- **`-c` 或 --count** : 计算符合样式的列数。
- **`-C`<显示行数> 或 --context=<显示行数>或-<显示行数>** : 除了显示符合样式的那一行之外，并显示该行之前后的内容。
- **`-d` <动作> 或 --directories=<动作>** : 当指定要查找的是目录而非文件时，必须使用这项参数，否则grep指令将回报信息并停止动作。
- **`-e`<范本样式> 或 --regexp=<范本样式>** : 指定字符串做为查找文件内容的样式。
- **`-E` 或 --extended-regexp** : 将样式为延伸的正则表达式来使用。
- **`-f`<规则文件> 或 --file=<规则文件>** : 指定规则文件，其内容含有一个或多个规则样式，让grep查找符合规则条件的文件内容，格式为每行一个规则样式。
- **`-F` 或 --fixed-regexp** : 将样式视为固定字符串的列表。
- **`-G` 或 --basic-regexp** : 将样式视为普通的表示法来使用。
- **`-h` 或 --no-filename** : 在显示符合样式的那一行之前，不标示该行所属的文件名称。
- **`-H` 或 --with-filename** : 在显示符合样式的那一行之前，表示该行所属的文件名称。
- **`-i` 或 --ignore-case** : 忽略字符大小写的差别。
- **`-l` 或 --file-with-matches** : 列出文件内容符合指定的样式的文件名称。
- **`-L` 或 --files-without-match** : 列出文件内容不符合指定的样式的文件名称。
- **`-n` 或 --line-number** : 在显示符合样式的那一行之前，标示出该行的列数编号。
- **`-o` 或 --only-matching** : 只显示匹配PATTERN 部分。
- **`-q` 或 --quiet或--silent** : 不显示任何信息。
- **`-r` 或 --recursive** : 此参数的效果和指定"-d recurse"参数相同。
- **`-s` 或 --no-messages** : 不显示错误信息。
- **`-v` 或 --invert-match** : 显示不包含匹配文本的所有行。
- **`-V` 或 --version** : 显示版本信息。
- **`-w` 或 --word-regexp** : 只显示全字符合的列。
- **`-x` --line-regexp** : 只显示全列符合的列。
- **`-y`** : 此参数的效果和指定"-i"参数相同。

### 实例

1、在文件 file.txt 中查找字符串 "hello"，并打印匹配的行：

```bash
grep hello file.txt
```

2、在文件夹 dir 中递归查找所有文件中匹配正则表达式 "pattern" 的行，并打印匹配行所在的文件名和行号：

```bash
grep -r -n pattern dir/
```

3、在标准输入中查找字符串 "world"，并只打印匹配的行数：

```bash
echo "hello world" | grep -c world
```

4、在当前目录中，查找后缀有 file 字样的文件中包含 test 字符串的文件，并打印出该字符串的行。此时，可以使用如下命令：

```bash
grep test *file 
```

结果如下所示：

```bash
$ grep test test* #查找前缀有“test”的文件包含“test”字符串的文件  
testfile1:This a Linux testfile! #列出testfile1 文件中包含test字符的行  
testfile_2:This is a linux testfile! #列出testfile_2 文件中包含test字符的行  
testfile_2:Linux test #列出testfile_2 文件中包含test字符的行 
```

5、以递归的方式查找符合条件的文件。例如，查找指定目录/etc/acpi 及其子目录（如果存在子目录的话）下所有文件中包含字符串"update"的文件，并打印出该字符串所在行的内容，使用的命令为：

```bash
grep -r update /etc/acpi 
```

输出结果如下：

```bash
$ grep -r update /etc/acpi #以递归的方式查找“etc/acpi”  
#下包含“update”的文件  
/etc/acpi/ac.d/85-anacron.sh:# (Things like the slocate updatedb cause a lot of IO.)  
Rather than  
/etc/acpi/resume.d/85-anacron.sh:# (Things like the slocate updatedb cause a lot of  
IO.) Rather than  
/etc/acpi/events/thinkpad-cmos:action=/usr/sbin/thinkpad-keys--update 
```

6、反向查找。前面各个例子是查找并打印出符合条件的行，通过"-v"参数可以打印出不符合条件行的内容。

查找文件名中包含 test 的文件中不包含test 的行，此时，使用的命令为：

```bash
grep -v test *test*
```

结果如下所示：

```bash
$ grep-v test* #查找文件名中包含test 的文件中不包含test 的行  
testfile1:helLinux!  
testfile1:Linis a free Unix-type operating system.  
testfile1:Lin  
testfile_1:HELLO LINUX!  
testfile_1:LINUX IS A FREE UNIX-TYPE OPTERATING SYSTEM.  
testfile_1:THIS IS A LINUX TESTFILE!  
testfile_2:HELLO LINUX!  
testfile_2:Linux is a free unix-type opterating system.  
```