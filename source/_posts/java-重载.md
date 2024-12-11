---
title: java 重载
date: 2024-12-08 16:37:16
tags:
- java
---
## 重载的好处
1) 减轻了起名的麻烦
2) 减轻了记名的麻烦
```java
public class OverLoad01 {
//编写一个 main 方法
    public static void main(String[] args) {
    // System.out.println(100);
    // System.out.println("hello,world");
    // System.out.println('h');
    // System.out.println(1.1);
    // System.out.println(true);
    //
    MyCalculator mc = new MyCalculator();
    System.out.println(mc.calculate(1, 2));
    System.out.println(mc.calculate(1.1, 2));
    System.out.println(mc.calculate(1, 2.1));
    }
}
class MyCalculator {
//下面的四个 calculate 方法构成了重载
//两个整数的和
    public int calculate(int n1, int n2) {
        System.out.println("calculate(int n1, int n2) 被调用");
        return n1 + n2;
    }
    //没有构成方法重载, 仍然是错误的，因为是方法的重复定义
    // public void calculate(int n1, int n2) {
    // System.out.println("calculate(int n1, int n2) 被调用");
    // int res = n1 + n2;
    // }
    //看看下面是否构成重载, 没有构成，而是方法的重复定义,就错了
    // public int calculate(int a1, int a2) {
    // System.out.println("calculate(int n1, int n2) 被调用");
    // return a1 + a2;
    // }
    //一个整数，一个 double 的和
    public double calculate(int n1, double n2) {
        return n1 + n2;
    }
    //一个 double ,一个 Int 和
    public double calculate(double n1, int n2) {
        System.out.println("calculate(double n1, int n2) 被调用..");
        return n1 + n2;
    }
    //三个 int 的和
    public int calculate(int n1, int n2,int n3) {
        return n1 + n2 + n2;
    }
}
```
## 注意事项以及使用细节
1. 方法名:必须相同
2. 形参列表:必须不同(形参类型或个数或顺序,至少有一样不同,参数名无要求)
3. 返回类型:无要求
## 练习
1.判断题:
与voidshow(int a,char b,doublec){}构成重载的有:[_2 3 4 5_]
```java
1. void show(int x,char y,double z){} //不是
2. int show(int a,double c,char b){} //是
3. void show(int a ,double c,char b){}//是
4. boolean show(int c,char b){}//是
5. void show(double c){} //是
6. double show(int x,char y,double z){} //不是
7. voidshows(){}//不是
```
