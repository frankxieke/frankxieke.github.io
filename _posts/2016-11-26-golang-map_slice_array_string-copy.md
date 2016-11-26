---
layout: post
title: golang map_slice_array_string copy
subtitle: golang map_slice_array_string copy
author: frank
date: 2016-11-26 18:58:50 +0800
categories: tech
tag: tech
---
````golang code array
package main

import (
    "fmt"
)

func main() {
    arr := [...]int{1, 2, 3}
    //打印初始的指针
    fmt.Printf("the pointer is : %p \n", &arr)
    printPointer(arr)
}

func printPointer(any interface{}) {
    fmt.Printf("the pointer is : %p \n", &any)
}
````

````Result
the pointer is : 0xc082008580
the pointer is : 0xc0820001d0
````

````golang Slice
package main

import (
    "fmt"
)

func main() {
    arr := make([]int, 3)
    //打印初始的指针
    fmt.Printf("the pointer is : %p \n", arr)
    printPointer(arr)
}

func printPointer(any interface{}) {
    fmt.Printf("the pointer is : %p \n", any)
}
````

````Result
the pointer is : 0xc082008580
the pointer is : 0xc082008580
````

````golang map
package main

import (
    "fmt"
)

func main() {
    arr := make(map[int]string)
    //arr := [3]int{1, 2, 3}
    //打印初始的指针
    fmt.Printf("the pointer is : %p \n", arr)
    printPointer(arr)
}

func printPointer(any interface{}) {
    fmt.Printf("the pointer is : %p \n", any)
}
````

````Result
the pointer is : 0xc082007c80
the pointer is : 0xc082007c80
````
