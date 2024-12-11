---
title: java可变参数
date: 2024-12-10 22:21:56
tags:
- java
---
## 基本概念
java 允许将同一个类中多个同名同功能但参数个数不同的方法，封装成一个方法。就可以通过可变参数实现。

## 基本语法
访问修饰符 返回类型 方法名(数据类型... 形参名) {  
}

## 快速入门案例
### 计算 2 个数的和，3 个数的和 .......
```java
public class VarParameter01 {
    //编写一个 main 方法
    public static void main(String[] args) {
        HspMethod m = new HspMethod();
        System.out.println(m.sum(1, 5, 100)); //106
        System.out.println(m.sum(1,19)); //20
    }
}
class HspMethod {
//可以计算 2 个数的和，3 个数的和 ， 4. 5， 。。
//可以使用方法重载
// public int sum(int n1, int n2) {//2 个数的和
// return n1 + n2;
// }
// public int sum(int n1, int n2, int n3) {//3 个数的和
// return n1 + n2 + n3;
// }
// public int sum(int n1, int n2, int n3, int n4) {//4 个数的和
// return n1 + n2 + n3 + n4;
// }
//..... //上面的三个方法名称相同，功能相同, 参数个数不同-> 使用可变参数优化

//解读
//1. int... 表示接受的是可变参数，类型是 int ,即可以接收多个 int(0-多)
//2. 使用可变参数时，可以当做数组来使用 即 nums 可以当做数组
//3. 遍历 nums 求和即可
    public int sum(int... nums) {
        //System.out.println("接收的参数个数=" + nums.length);
        int res = 0;
        for(int i = 0; i < nums.length; i++) {
        res += nums[i];
        }
        return res;
        }
}
```
## 注意事项和使用细节
1. 可变参数的实参可以为0个或任意多个。
2. 可变参数的实参可以为数组。
3. 可变参数的本质就是数组.
4. 可变参数可以和普通类型的参数一起放在形参列表,但必须保证可变参数在最后
5. 一个形参列表中只能出现一个可变参数
```java
public class VarParameterDetail {
    //编写一个 main 方法
    public static void main(String[] args) {
    //细节: 可变参数的实参可以为数组
    int[] arr = {1, 2, 3};
    T t1 = new T();
    t1.f1(arr);
    }
}
class T {
    public void f1(int... nums) {
        System.out.println("长度=" + nums.length);
    }
    //细节: 可变参数可以和普通类型的参数一起放在形参列表，但必须保证可变参数在最后
    public void f2(String str, double... nums) {
    }
    //细节: 一个形参列表中只能出现一个可变参数
    //下面的写法是错的. // public void f3(int... nums1, double... nums2) {
    // }
}
```