**命令格式：**

head [参数] [文件]  

**参数：**

- `-q` 隐藏文件名
- `-v` 显示文件名
- `-c`<数目> 显示的字节数。
- `-n`<行数> 显示的行数。

**实例**

要显示 runoob_notes.log 文件的开头 10 行，请输入以下命令(默认带参赛 -n 10)：
```bash
head runoob_notes.log
```


以上命令等价于：
```bash
head -n 10 runoon_notes.log
```
显示 notes.log 文件的开头 5 行，请输入以下命令：
```bash
head -n 5 runoob_notes.log
```
显示文件前 20 个字节:
```bash
head -c 20 runoob_notes.log
```