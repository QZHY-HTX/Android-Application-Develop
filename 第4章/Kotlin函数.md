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

