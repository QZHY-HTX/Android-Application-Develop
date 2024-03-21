## 函数
```kotlin
fun hello(){
    return println("hello, world")
}

fun main(){
    hello()
}
```

- 两数相加的函数

```kotlin
fun sum(x:Int, y:Int): Int {
    return x+y
}

fun main(){
    println(sum(1,2))
}
```

- 带字符串模版的函数
```kotlin
fun printMessageWithPrefix(message: String, prefix: String) {
    println("[$prefix] $message")
}

fun main() {
    printMessageWithPrefix(prefix = "Log", message = "Hello")
    // [Log] Hello
}
```

- 默认参数值

```kotlin
fun printMessageWithPrefix(message: String, prefix: String = "Info") {
    println("[$prefix] $message")
}

fun main() {
    printMessageWithPrefix("Hello", "Log") 
    // [Log] Hello
    
    printMessageWithPrefix("Hello")        
    // [Info] Hello
    
    printMessageWithPrefix(prefix = "Log", message = "Hello")
    // [Log] Hello
}
```

- 无返回值的函数

```kotlin
fun printMessage(message: String) {
    println(message)
}

fun main() {
    printMessage("Hello")
    // Hello
}
```

- 单一表达式函数

```kotlin
fun sum(x: Int, y: Int): Int {
    return x + y
}

fun mul(x: Int, y: Int) = x * y

fun main() {
    println(sum(1, 2))
    println(mul(2, 2))
    // 3
}
```

---

## 练习

1. 请你写一个函数计算圆的面积

```kotlin
import kotlin.math.PI

fun circleArea() {
    // 请在此处补充代码
}
fun main() {
    println(circleArea(2))
}
```

<details>
<summary>点击查看解决方案</summary>

```kotlin
import kotlin.math.PI

fun circleArea(r: Int) : Double{
    // 请在此处补充代码
    return r*r*Math.PI
}
fun main() {
    println(circleArea(2))
}
```
</details>

---

2. 将刚刚写的函数重写为单一表达式函数

<details>
<summary>点击查看解决方案</summary>

```kotlin
import kotlin.math.PI

fun circleArea(radius: Int): Double = PI * radius * radius

fun main() {
    println(circleArea(2)) // 12.566370614359172
}
```
</details>

---

3. 时间秒数转换器，请把时-分-秒换转成秒

<details>
<summary>点击查看解决方案</summary>

```kotlin
fun intervalInSeconds(hours: Int, minutes: Int, seconds: Int) =
    ((hours * 60) + minutes) * 60 + seconds

fun main() {
    println(intervalInSeconds(1, 20, 15))
    println(intervalInSeconds(0, 1, 25))
    println(intervalInSeconds(2, 0, 0))
    println(intervalInSeconds(0, 10, 0))
    println(intervalInSeconds(1, 0, 1))
}
```
</details>

