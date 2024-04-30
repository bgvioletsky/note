---
sticker: lucide//atom
---
# Go 语言指针

Go 语言中指针是很容易学习的，Go 语言中使用指针可以更简单的执行一些任务。

接下来让我们来一步步学习 Go 语言指针。

我们都知道，变量是一种使用方便的占位符，用于引用计算机内存地址。

Go 语言的取地址符是 &，放到一个变量前使用就会返回相应变量的内存地址。

以下实例演示了变量在内存中地址：

## 实例
```go
package main  
  
import "fmt"  
  
func main() {  
   var a int = 10    
    fmt.Println(bg(a))
   fmt.Printf("变量的地址: %x\n", &a  )  
}  
func bg(a int) int {
	var b int =12
	x:= &b
	*x=a
	return b
}
```

执行以上代码输出结果为：
```go
变量的地址: 20818a220
```
**创建指针的另一种方式new()函数**
```go
//new(类型)
	str:=new(string)
	*str="bgcode"
	fmt.Print(*str)
```

# Go 语言结构体
## 定义结构体

结构体定义需要使用 type 和 struct 语句。struct 语句定义一个新的数据类型，结构体中有一个或多个成员。type 语句设定了结构体的名称。结构体的格式如下：

```go
type struct_variable_type struct {
   member definition
   member definition
   ...
   member definition
}```
