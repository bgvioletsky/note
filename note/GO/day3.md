---
sticker: lucide//atom
---
## 类型

#### 浮点数
float64
float32
```go
var sa float64=212.21
var year int = 2018
```
#### 整数
int 有符号包括负数
uint 无符号
包括8 、16、32、64等位数
颜色使用uint8类型
%b能以2进制的方式输出整数的值
```go
var blue uint8 = 255
fmt.Printf ("%08b\n", blue); blue++
fmt.Printf ("%08b\n", blue)
```
在Go语言中，`fmt.Printf("%08b\n", blue)`中的`%08`是一个格式化动词，用于指定打印的格式。具体来说：
- `%`：表示格式化动词的开始
- `0`：表示用0来填充输出的结果
- `8`：表示输出的总长度为8个字符，不足8个字符时会在左侧用0填充
- `b`：表示以二进制形式输出整数

因此，`%08b`表示以二进制形式输出整数，并且总长度为8个字符，不足8个字符时用0填充。
#### big包
使用方法
```go
lightSpeed =: big.NewInt (299792)
secondsPerDay =: big.NewInt (86400)
secondsPerDay =: new (big.Int); secondsPerDay. SetString ("86400", 10)
```

#### 字符串
```go
a:="sad"
var a="sad"
var a string ="asda"
var as string
//单引号表示字符如
var grade ='A'
var grade rune ='A'
```

#### 数字类型转换

```go
age =: 41
marsAge := float64 (age)
```