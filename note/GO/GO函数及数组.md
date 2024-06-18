---
sticker: lucide//atom
---
## 构建块
### 函数
```go
/* 定义结构体 */  
type Circle struct {  
  radius float64  
}
func Intn(n Circle) Circle{
	s:=2
	return s*n+2*n
}
//Intn函数名
//n Circle 传入参数类型与传入参数名
//Circle 返回类型
num :=rand.Intn(10)
```
#### 匿名函数
```go
sad:=func (sd string){
  fmt.Print(sd)
}
func (){
	sad("sdasd")
}()
```
#### 数组
`var arrayName [size]dataType`:其中，**arrayName** 是数组的名称，**size** 是数组的大小，**dataType** 是数组中元素的数据类型。
以下定义了数组 balance 长度为 10 类型为 float32：
```go
var balance [10]float32
```
## 初始化数组
```go
var numbers [5]int
var numbers = [5]int{1, 2, 3, 4, 5}
numbers := [5]int{1, 2, 3, 4, 5}
var balance = [5]float32{1000.0, 2.0, 3.4, 7.0, 50.0}
balance := [5]float32{1000.0, 2.0, 3.4, 7.0, 50.0}
var balance = [...]float32{1000.0, 2.0, 3.4, 7.0, 50.0}
或
balance := [...]float32{1000.0, 2.0, 3.4, 7.0, 50.0}
//  将索引为 1 和 3 的元素初始化
balance := [5]float32{1:2.0,3:7.0}
balance[4] = 50.0
var salary float32 = balance[9]

```
循环遍历数组
```go
da:=[5]float32{1000.0, 2.0, 3.4, 7.0, 50.0}
for i:=0;i<len(da);i++{
	fmt.Print(da[i])
}
for i ,da :=range da{
fmt.Print(da)
fmt.Print(i)
}
```