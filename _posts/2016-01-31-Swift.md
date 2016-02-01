---
layout: post
title:  "swift 基础(控制流)"
subtitle: ""
date:   2016-01-31
categories: swift
---

# switch - 值绑定

```swift
let 坐标 = (1,7)

switch 坐标 {
    case (let x,0):"X轴上的值是\(x)"
    case (0,let y):"Y轴上的值是\(y)"
    case (let x,let y):"X轴上的值是\(x),Y轴上的值是\(y)"//x轴上的值是1，Y轴上的值是7
    }
```

# switch - 值绑定 where 筛选



```swift
let 坐标 = (2,2)
switch 坐标 {
    case let(x,y) where x == y : "(\(x),\(y))的横坐标和纵坐标相等"//print (2,2)的横坐标和纵坐标相等
     case let(x,y) where (x > 0 && y > 0) : "(\(x),\(y))在第一象限"//只执行第一个，就不会往下执行了
     case let(x,y) : "x轴上的值\(x),y轴上的值是\(y)"
}

```



