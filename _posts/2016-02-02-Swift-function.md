---
layout: post
title:  "swift 基础(函数)"
subtitle: "function"
date:   2016-01-31
categories: swift
---

# In-Out 参数


```swift
var a = 1
var b = 2

func swapTwoInts (inout a:Int,inout _ b:Int){
    let temporaryA = a
    a = b
    b = temporaryA
}

swapTwoInts(&a, &b)


a //  2
b //  1
```


