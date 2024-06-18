---
sticker: lucide//atom
tags:
  - code
  - go
  - shell
  - mit
---
```go
file,err :os.Open(filename)//打开文件
if err !=nil{
	return ""
}//为空返回空
defer file.Close()//关闭文件
```