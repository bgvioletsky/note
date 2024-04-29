---
sticker: lucide//atom
---
<font color="#e5b9b7">Go对于大括号{}的摆放位置非常挑剔。在代码中，左大括号{与func 关键字位于同一行，而右大括号}则独占一行。这是Go语言唯 一允许的大括号放置风格，除此之 外的其他大括号放置风格都是不被允许的。</font>
### 常量变量

定义常量：

```go
const bg = "dad"

```
定义变量方式：

```go
var sd = 21
var (
	dis = 213
	dsd = 412
)//定义多个变量
var kk, nn = 21 ,21
kk :=21
```

导入包
```go
package main

import (
	"fmt"
	"math/rand"//包名
)
```

###  逻辑运算符
`==` 相等
`!=` 不等
`<` 小于
`>` 大于
`<=` 小于等于
`>=` 大于等于
`||` 存在一个为真则为真
`&&`存在一个为假则全为假
### 循环和分支

```go
package main
import (
	"fmt"
	"strings"
)
func main() {
	fmt.Println("my friend")
	a := 1
	if a == 2 {
		fmt.Println("my friend")
	} else if a == 1 {
		fmt.Println("my friend1")
	} else {
		fmt.Println("my friend2")
	}
	switch {
	case a == 2 :
		fmt.Println("my friend")
	case a == 3 :
		fmt.Println("my friend")	
	case a == 4 :
		fmt.Println("my friend")
	}
	ax := 10
	for ax > 0 {
		fmt.Println(ax)
		ax--
	}
	bg := 12
	for {
		fmt.Println(bg)
		bg++
		if bg >= 23 {
			bg = 12
		    if rand.Intn(2) == 0 {
			     braek
		    }
		}
	}
}
```
<font color="#ccc1d9">test 关于go的流程控制</font>
```go
package main  
  
import (  
    "fmt"  
    "math/rand")  
  
func main() {  
    a := 21  
    for {  
       var b = rand.Intn(100)  
       if b == a {  
          fmt.Printf("你的号码是%d", a)  
          break  
       } else if b < a {  
          fmt.Println("小了")  
       } else {  
          fmt.Println("大了")  
       }  
  
    }  
    for count := 10; count >0 ;count--{
	    fmt.Println("das")
    }
}
```

### 作用域
简短声明为var 关键字提供了另一种备选语法 。以下两行代码是完全等效的:
```go
	var count = 10 
	count:= 10
```
初看上去，少键入两三个字符似乎不算什么，但正是这一点使得简短声明比var 关键字流行得多。更重要的是，简短声明还可以用在 一些无法使用var 关键字的地方。
代码清单4-2展示了f or 循环的一种变体形式，它包含了初始化语句、比较条件语句以 及对count 变量执行递减运算的后置语句。在使用这种形式的f or 循环时，我们需要依次 向循环提供初始化语句、比较条件语句和后置语句。
1. 作用域可以让我们在多个位置使用相同的变量名而不会引发任何冲突，并且在编程的时候只需要考虑位 于当前作用域之内的变量。
2. 脱离作用域的变量将不再可见并且无法访问。尝试在num变量的作用域之外访问它将导致Go编译器报告错 误 