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

# 控制转移语句

**continue**
 * 用于循环语句中，使执行下次循环
 
 
```swift
let puzzleInput = "great minds think alike"
var puzzleOutput = ""
for character in puzzleInput.characters{
    switch character{
    case "a","e","i","o","u"," ":
        continue //执行下次循环
    default:
        puzzleOutput.append(character)
    }
}


print(puzzleOutput) //print grtmndsthnklk
```

**break**
* 可用于switch，循环语句

```swift
let puzzleInput = "great minds think alike"
var puzzleOutput = ""
for character in puzzleInput.characters{
    switch character{
    case "a","e","i","o","u"," ":
        break // 跳出 switch执行下面语句
        //这里如果 continue  是执行下次循环 switch 以下的代码都不会执行 ，而break是跳出switch会执行下面代码
    default:
        puzzleOutput.append(character)
    }
    break // 跳出for循环
}
```

**fallthrough**
* 用于switch语句

```swift
let puzzleInput = "great minds think alike"
var puzzleOutput = ""
for character in puzzleInput.characters{
    switch character{
    case "a":fallthrough
    case "e":fallthrough
    case "i":fallthrough
    case "o":fallthrough
    case "u":fallthrough
    case " ":continue
    default:
        puzzleOutput.append(character)
    }
}

print(puzzleOutput) //print grtmndsthnklk

```


# 标签语句

给流程语句打标签


```swift

let puzzleInput = "great minds think alike"
var puzzleOutput = ""
gameloop : for character in puzzleInput.characters{
    switch character{
    case "a","e","i","o","u"," ":
        break gameloop
    default:
        puzzleOutput.append(character)
    }
}

print(puzzleOutput) //print gr



```


