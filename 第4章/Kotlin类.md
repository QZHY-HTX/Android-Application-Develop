## Class

和其他面向对象的语言一样，Kotlin 同样支持类和对象，使用 `class` 关键字声明类，同时也可以通过类创建对象，从而包含特定的一组特征。

例如

```kotlin
class Customer
```

同时还可以在创建类的时候声明一些类的属性，例如

```kotlin
class Contact(val id: Int, var email: String)
```

或者

```kotlin
class Contact(val id: Int, var email: String) {
    val category: String = ""
}
```

如果属性无需反复修改，那么可以使用`val`进行定义，如果需要，则采用`var`

当然也可以提前先准备好初始的默认赋值

```kotlin
class Contact(
    val id: Int, 
    var email: String = "abc@qq.com"
){
    val category: String = "work"
}
```

使用主函数，体验一下类的使用

```kotlin
class Contact(val id: Int, var email: String)

fun main() {
    val contact = Contact(1, "abc@qq.com")
    
    println(contact.email)           

    contact.email = "xyz@qq.com"

    println(contact.email)           
}
```

## 成员方法

```kotlin
class Contact(val id: Int, var email: String) {
    fun printId() {
        println(id)
    }
    //补充输出邮箱的函数
    fun printEmail() {
        println(email)
    }
}

fun main() {
    val contact = Contact(1, "abc@qq.com")

    contact.printId()           
    // 1
    contact.printEmail()
    //abc@qq.com
}
```

## Data Class

kotlin 具有数据类，可以非常方便地进行数据操作，在类前补充 `data` 即可

```kotlin
data class User(val name: String, val id: Int)
```

|函数|描述|
|:--|:--|
|`.toString()`|打印数据类的信息|
|`.equals()` or `==`|和其他实例进行比较|
|`.copy()`|复制另一个类的实例来创建类实例|

```kotlin
data class User(val name: String, val id: Int)

fun main(){
    val user = User("Alex", 1)
    val secondUser = User("Alex", 1)
    val thirdUser = User("Max", 2)

    // Compares user to second user
    println("user == secondUser: ${user == secondUser}") 
    // user == secondUser: true

    // Compares user to third user
    println("user == thirdUser: ${user == thirdUser}")   
    // user == thirdUser: false
}
```

```kotlin
data class User(val name: String, val id: Int)

fun main(){
    val user = User("Alex", 1)

    // Creates an exact copy of user
    println(user.copy())       
    // User(name=Alex, id=1)

    // Creates a copy of user with name: "Max"
    println(user.copy("Max"))  
    // User(name=Max, id=1)

    // Creates a copy of user with id: 3
    println(user.copy(id=3)) 
    // User(name=Alex, id=3)
}
```

如果要通过 `copy()` 修改实例信息，请确保你所输入的形参对应是正确的。

---

## 练习

1. 定义一个具有两个属性的数据类`Employee`：一个表示姓名，一个表示工资，确保工资是可变的，否则将无法升职加薪。最后通过主函数进行演示：

```kotlin
// 在此处补充代码

fun main() {
    val emp = Employee("htx", 20)
    println(emp)
    emp.salary += 10
    println(emp)
}
```

<details>
<summary>点击查看解决方案</summary>

```kotlin
data class Employee(val name: String, var salary: Int)

fun main() {
    val emp = Employee("Mary", 20)
    println(emp)
    emp.salary += 10
    println(emp)
}
```
</details>

---

2. 创建一个随机员工生成器，定义一个具有固定潜在名称列表的类，这个类有最低和最高工资共同构成，然后在主函数中演示这个类的使用方法。

```kotlin
import kotlin.random.Random

data class Employee(val name: String, var salary: Int)

// 在此处补充代码

fun main() {
    val empGen = RandomEmployeeGenerator(10, 30)
    println(empGen.generateEmployee())
    println(empGen.generateEmployee())
    println(empGen.generateEmployee())
    empGen.minSalary = 50
    empGen.maxSalary = 100
    println(empGen.generateEmployee())
}
```

<details>
<summary>点击查看解决方案</summary>

```kotlin
import kotlin.random.Random

data class Employee(val name: String, var salary: Int)

class RandomEmployeeGenerator(var minSalary: Int, var maxSalary: Int) {
    val names = listOf("张三", "李四", "王五", "赵六", "钱七", "薛八")
    fun generateEmployee() =
        Employee(names.random(),
            Random.nextInt(from = minSalary, until = maxSalary))
}

fun main() {
    val empGen = RandomEmployeeGenerator(10, 30)
    println(empGen.generateEmployee())
    println(empGen.generateEmployee())
    println(empGen.generateEmployee())
    empGen.minSalary = 50
    empGen.maxSalary = 100
    println(empGen.generateEmployee())
}
```
</details>