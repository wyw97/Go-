# Go
上学期需要使用go语言的时候没有好好珍惜，现在开始补补吧。

入门部分：
go语言的安装直接在官网上看document即可。
hello world示例


package main

import "fmt"

func main(){
    fmt.Println("Hello World!")
}


在终端中，可以通过命令  go run helloworld.go运行程序
也可以编译生成可执行文件，这样以后可以随时执行。
命令如下：

go build helloworld.go

./helloworld

命令行传递参数示例

package main

import(
 
 "fmt"
 
 "os"

)

func main(){

    var s, sep string
  
    for i := 1; i < len(os.Args); i++{
    
        s += sep + os.Args[i]
      
        sep = " "
  
  }  
  
  fmt.Println(s)

}


for语句的使用方法：

for initialization;condition;port{

...

}

类似于C语言while的for循环格式

for condition{

 ...

}

更进一步，可以写成如下形式：

for {

 ...

}

循环的终止条件可以是break 或者 return


下面来看for循环的另外一个例子，在这个例子中可以同时在for语句中赋值多个变量

package main

import(

    "fmt"
  
    "os"

)

func main(){

    s,sep := "",""
    
    for _, arg := range os.Args[1:] {
    
       s += sep + arg
       
       sep = " " 
   
   }
   
   fmt.Println(s)
   
}

Go语言的Range函数：
range函数是个神奇有趣的内置函数，可以使用它来遍历数组，切片和字典。
当用于遍历数组和切片的时候，range函数返回的是索引和元素；
当用于遍历字典的时候，range函数返回字典的键和值。

Attention，在go语言中，出现了未使用的局部变量是不允许的，会compile error，在go语言中可以使用_来忽略这个返回值。

定义字符串变量的几种方式,注意不同方式的使用方式。推荐使用前两种。

s := ""   注意：it may be used only within a function, not for package-level variables.

var s string  注意：string变量默认为""

var s = ""

var s string = ""

字符串的复制会产生浪费，一种解决方式是使用strings包中的join函数。

func main(){
 
     fmt.Println(strings.Join(os.Args[1:],""))

}





