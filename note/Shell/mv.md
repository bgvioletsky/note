---
tags:
  - shell
  - mit
  - code
---

### 语法

```bash
mv [options] source dest
mv [options] source... directory
```

**参数说明**：

**-b**: 当目标文件或目录存在时，在执行覆盖前，会为其创建一个备份。

**-i**: 如果指定移动的源目录或文件与目标的目录或文件同名，则会先询问是否覆盖旧文件，输入 y 表示直接覆盖，输入 n 表示取消该操作。

**-f**: 如果指定移动的源目录或文件与目标的目录或文件同名，不会询问，直接覆盖旧文件。

**-n**: 不要覆盖任何已存在的文件或目录。

**-u**：当源文件比目标文件新或者目标文件不存在时，才执行移动操作。

mv 参数设置与运行结果

| 命令格式                                         | 运行结果                                                                                                                             |
| :------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| `mv source_file(文件) dest_file(文件)`           | 将源文件名 source_file 改为目标文件名 dest_file                                                                                              |
| `mv source_file(文件) dest_directory(目录)`      | 将文件 source_file 移动到目标目录 dest_directory 中                                                                                         |
| `mv source_directory(目录) dest_directory(目录)` | 目录名 dest_directory 已存在，将 source_directory 移动到目录名 dest_directory 中；目录名 dest_directory 不存在则 source_directory 改名为目录名 dest_directory |
| `mv source_directory(目录) dest_file(文件)`      | 出错                                                                                                                               |
