## if

```kotlin
fun main(){
    val a : Int
    val check : Boolean = true
    if(check){
        a = 1
    }else{
        a = 2
    }
    println(a)
}
```

或者省略某些花括号

```kotlin
fun main(){
    val a = 1
    val b = 2
    println( if (a<b) a else b)
}
```

## when

这个语句很像 switch

```kotlin
fun main(){
    val obj = "Hello"
    when(obj){
        "1" -> println("One")
        "Hello" -> println("Greeting")
        else -> println("Unknown")
    }
}
```

或者

```kotlin
fun main(){
    val temp = -1
    val description = when{
        temp < 0 -> "very good"
        temp < 10 -> "a bit cold"
        temp < 20 -> "warm"
        else -> "hot"
    }
    println(description)
}
```

## ranges

1..4

'A'..'Z'

'A'..'Z' step 2

'A' downTo 'Z' step 2

##
```kotlin
fun main(){
    for (num in 1..5){
        println(num)
    }
}
```

## Loops
- for

```kotlin
fun main(){
    for(num in 1..5){
        println(num)
    }
}
```

```kotlin
fun main(){
    val cakes = listOf("carrot", "cheese", "chocolate")
    for(cake in cakes){
        println("Yummy, it's a $cake cake!")
    }
}
```

- while
```kotlin
fun main(){
    var cakesEaten = 0
    while(cakesEaten<3){
        println("Eat a cake")
        cakesEaten++
    }
}
```

```kotlin
fun main(){
    var cakesEaten = 0
    var cakesBaked = 0
    while(cakesEaten<3){
        println("Eat a cake")
        cakesEaten++
    }
    do{
        println("Bake a cake")
        cakesBaked++
    }while(cakesBaked < cakesEaten)
}
```

## 做个练习

1. 循环获得从 1 ～ 15 的数，>= 5 输出，<5 不输出

```kotlin
fun main(){
    for(num in 1..15){
        if(num>=5){
            println(num)
        }
    }
}
```

---

2. 请使用 when 关键字完成以下信息的键值映射

|button|Action|
|:--|:--|
|A|Yes|
|B|No|
|X|Menu|
|Y|Nothing|
|Other|There is no such button|

```kotlin
fun main() {
    val button = "A"

    println(
        // Write your code here
    )
}
```

<details>
<summary>点击查看解决方案</summary>

```kotlin
fun main() {
    val button = "A"

    println(
        when (button) {
            "A" -> "Yes"
            "B" -> "No"
            "X" -> "Menu"
            "Y" -> "Nothing"
            else -> "There is no such button"
        }
    )
}
```
</details>

---

3. 你现在有一个程序可以计算你现在持有的披萨碎片，当你拥有八个披萨碎片的时候，你就有一整个披萨了，现在请你用 `while` 和 `do-while`重构这个代码

```kotlin
fun main() {
    var pizzaSlices = 0
    // Start refactoring here
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    println("现在只有 $pizzaSlices 个披萨碎片 :(")
    pizzaSlices++
    // End refactoring here
    println("现在有 $pizzaSlices 个披萨碎片啦！我们获得了一整个完整的披萨 :D")
}
```

<details>
<summary>点击查看 while 解决方案</summary>

```kotlin
fun main() {
    var pizzaSlices = 0
    while ( pizzaSlices < 7 ) {
        pizzaSlices++
        println("现在只有 $pizzaSlices 个披萨碎片 :(")
    }
    pizzaSlices++
    println("现在有 $pizzaSlices 个披萨碎片啦！我们获得了一整个完整的披萨 :D")
}
```
</details>

<details>
<summary>点击查看 do-while 解决方案</summary>

```kotlin
fun main() {
    var pizzaSlices = 0
    pizzaSlices++
    do {
        println("现在只有 $pizzaSlices 个披萨碎片 :(")
        pizzaSlices++
    } while ( pizzaSlices < 8 )
    println("现在有 $pizzaSlices 个披萨碎片啦！我们获得了一整个完整的披萨 :D")
}
```
</details>

---

4. 你现在有一个单词数组，请你使用 `for` 和 `if` 输出以 `l` 开头的单词。

```kotlin
fun main() {
    val words = listOf("dinosaur", "limousine", "magazine", "language")
    // Write your code here
}
```

<details>
<summary>点击查看解决方案</summary>

```kotlin
fun main() {
    val words = listOf("dinosaur", "limousine", "magazine", "language")
    for (w in words) {
        if (w.startsWith("l"))
            println(w)
    }
}
```
</details>