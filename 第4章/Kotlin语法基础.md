# 学习资料
- 英语基础 - 非常重要，可以没办法看懂语法，但一定得看懂单词或者能说出来是最好的。

- Kotlin official tutorial：https://kotlinlang.org/docs/kotlin-tour-hello-world.html

- 在线编译器：https://play.kotlinlang.org/

---

# Hello World
这个示例描述如何使用 Kotlin 输出信息
```kotlin
fun main(){
    print("1. 我不会换行")
    println("2. 我会换行")
    println("3. 不信你看")
}
```

# 变量的声明区别
- `val` 是只读变量，不能再修改
- `var` 是可变变量，能够修改
- `$` 表示模版获值

```kotlin
fun main(){
    val a = 1
    var b = 1
    println("a = $a, b = $b")
    b = 2
    println("a = $a, b = $b")
}
```

# 基本类型

|类别|基本类型|
|:--|:--|
|整数|Byte,Short,Int,Long|
|无符号整数|UByte,UShort,UInt,ULong|
|浮点数|Float,Double|
|布尔|Boolean|
|字符|Char|
|字符串|String|

- 完整定义：`val a : Int = 1`
- 简写定义：`var a = 1`

# 集合

|集合类型|描述|
|:--|:--|
|Lists|有序的项目集合|
|Sets|唯一的无序项目集合|
|Maps|键值对构成的集合，其中键是唯一的，并且仅映射到一个值|

## List
```kotlin
fun main(){
    val shapes = listOf("A", "B", "C")
    println(shapes)
    println(shapes[0])
    println(shapes.first())
    println(shapes.count())
    println(shapes.last())
    println("A" in shapes)
    println("D" in shapes)
}
```

```kotlin
fun main(){
    val Shapes = mutableListOf("A","B","C")
    Shapes.add("D")
    println(Shapes)
    Shapes.remove("A")
    println(Shapes)
}
```

## Set
```kotlin
fun main(){
    val readOnlyFruit = setOf("apple","banana","cherry","cherry")
    println(readOnlyFruit)
}
```

```kotlin
fun main(){
    val Fruit = mutableSetOf("apple","banana","cherry","cherry")
    Fruit.add("pear")
    println(Fruit)
    Fruit.remove("apple")
    println(Fruit)
}
```