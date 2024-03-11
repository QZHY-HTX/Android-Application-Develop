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

## 做个练习

循环获得从 1 ～ 15 的数，>= 5 输出，<5 不输出

```kotlin
fun main(){
    for(num in 1..15){
        if(num>=5){
            println(num)
        }
    }
}
```