# 开发环境

- Windows 10 
- Java SE 8
- Android Studio 3.5.2
- Android 10（首次进行案例 1 使用 Android 5）

# 环境部署步骤

- 安装 Java SE 8
    - 下载 JDK 8 和 JRE 8 并完成环境配置
    - 配置 JAVA_HOME 和 Path
- 安装 Android Studio 3.5.2 
    - 参考教材
    - 先配置 SDK 然后配置 AVD 接着启动安卓虚拟设备
- 创建空项目 HiAndroid 并等待 Gradle 下载完成后进行运行
- PPT 中采用 Windows7 + Eclipse + JDK7 + ADT 共同部署，这种方式较为古老，作为课外了解
# HiAndroid 案例源码分析

```xml
<!--这是XML声明，指定了XML的版本（1.0）和编码（utf-8）-->
<?xml version="1.0" encoding="utf-8"?>
<!--ConstraintLayout 是 Android 中的一个布局容器，它允许通过约束条件来定位和调整其子视图-->
<androidx.constraintlayout.widget.ConstraintLayout
    //定义 Android 命名空间的 XML 命名空间前缀 android。这使得你可以在 XML 文件中使用 Android 特定的属性
    xmlns:android="http://schemas.android.com/apk/res/android"
    //定义 tools 命名空间，它通常用于在 Android Studio 中提供设计时的属性，这些属性不会影响运行时的行为
    xmlns:tools="http://schemas.android.com/tools"
    //定义 app 命名空间，它通常用于自定义属性或来自库的属性
    xmlns:app="http://schemas.android.com/apk/res-auto"
    //设置 ConstraintLayout 的宽度和高度以匹配其父容器的大小
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    指定这个布局与哪个活动（Activity）相关联。这主要用于在 Android Studio 的布局编辑器中提供上下文。
    tools:context=".MainActivity">
    <!--开始定义一个 TextView，它是一个用于显示文本的视图-->
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hi Android!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />
<!--结束constraintlayout的定义-->
</androidx.constraintlayout.widget.ConstraintLayout>
```

```Java
//这一行声明了这个类所在的包名。包名是用来组织和管理Java类的一种方式，也可以用来避免类名冲突
package com.example.hiandroid;
//这一行是一个导入语句，导入了 AndroidX 库中的 AppCompatActivity 类。AppCompatActivity 是 Android 应用开发中使用的一个基础类，用于创建具有兼容性的活动（Activity）
import androidx.appcompat.app.AppCompatActivity;
//这一行导入了 Android OS 包中的 Bundle 类。Bundle 通常用于在 Android 组件之间传递数据。
import android.os.Bundle;
//这一行声明了一个名为 MainActivity 的公共类，并且这个类继承自 AppCompatActivity。继承 AppCompatActivity 意味着这个类可以作为一个 Android 活动（Activity）来运行，并且具有兼容性特性
public class MainActivity extends AppCompatActivity {

    @Override
    //这一行定义了一个名为 onCreate 的方法，这是 Android 活动（Activity）生命周期中的一个重要方法。当活动被首次创建时，系统会调用这个方法。这个方法接受一个 Bundle 类型的参数，通常用于保存和恢复活动的状态信息。
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}
```