---
title: Java方法递归的调用
date: 2024-12-05 16:20:05
tags:
- java
---

## 基本介绍
简单的说: 递归就是**方法自己调用自己**,每次调用时传入不同的变量.递归有助于编程者解决复杂问题,同时可以让代码变得简洁。
## 递归有什么用
1. 各种数学问题如:8皇后问题,汉诺塔,阶乘问题,迷宫问题,球和篮子的向题(google编程
大赛)
2. 各种算法中也会使用到谨归,比如快排,归并排序,二分查找,分治算法等
3. 将用栈解决的问题->递归代码比较简洁
## 递归举例
列举两个小案例,来理解递归调用机制  
1) 打印问题
2) 阶乘问题  
```java
public class Recursion01 {
//编写一个 main 方法
    public static void main(String[] args) {
        T t1 = new T();
        t1.test(4);//输出什么？ n=2 n=3 n=4
        int res = t1.factorial(5);
        System.out.println("5 的阶乘 res =" + res);
    }
}
    class T {
    //分析
        public void test(int n) {
            if (n > 2) {
            test(n - 1);
        }
    System.out.println("n=" + n);
    }
    //factorial 阶乘
    public int factorial(int n) {
        if (n == 1) {
        return 1;
        } else {
            return factorial(n - 1) * n;
        }
    }
}
```
![](https://free4.yunpng.top/2024/12/08/675558a290f6d.png)
![](https://free4.yunpng.top/2024/12/08/67555890e813f.png)


## 递归重要规则
1. 执行一个方法时，就创建一个新的受保护的独立空间(栈空间)  
2. 方法的局部变量是独立的，不会相互影响，比如n变量  
3. 如果方法中使用的是引用类型变量(比如数组，对象),就会共享该引用类型的数据.
4. 递归必须向退出递归的条件逼近，否则就是无限递归，出现StackOverflowError,死龟了：)  
5. 当一个方法执行完毕，或者遇到return,就会返回，遵守谁调用，就将结果返回给谁，同时当方法执行完毕或者返回时，该方法也就执行完毕。

## 实例
1. 请使用建组的方式求被契数1,1,2，3，5，8，13…给你一个整数n,求出它的值是多  

2. 猴子吃桃子问题:有一堆桃子,猴子第一天吃了其中的一半,并再多吃了一个!以后
每天猴子都吃其中的一半,然后再多吃一个。当到第10天时,想再吃时(即没吃)
发现只有1个桃子了。问题:最初共多少个桃子?

```java
public class RecursionExercise01 {
    //编写一个 main 方法
    public static void main(String[] args) {
        T t1 = new T();
        // int n = 7;
        // int res = t1.fibonacci(n);
        // if(res != -1) {
        // System.out.println("当 n="+ n +" 对应的斐波那契数=" + res);
        // }
        //
        //桃子问题
        int day = 0;
        int peachNum = t1.peach(day);
        if(peachNum != -1) {
        System.out.println("第 " + day + "天有" + peachNum + "个桃子");
        }
    }
}
class T {
/*
请使用递归的方式求出斐波那契数 1,1,2,3,5,8,13...给你一个整数 n，求出它的值是多
思路分析
1. 当 n = 1 斐波那契数 是 1
2. 当 n = 2 斐波那契数 是 1
3. 当 n >= 3 斐波那契数 是前两个数的和
4. 这里就是一个递归的思路
*/
public int fibonacci(int n) {
    if( n >= 1) {
    if( n == 1 || n == 2) {
    return 1;
    } else {
    return fibonacci(n-1) + fibonacci(n-2);
    }
    } else {
    System.out.println("要求输入的 n>=1 的整数");
    return -1;
    }
}
韩顺平循序渐进学 Java 零基础
第 224页
/*
猴子吃桃子问题：有一堆桃子，猴子第一天吃了其中的一半，并再多吃了一个！
以后每天猴子都吃其中的一半，然后再多吃一个。当到第 10 天时，
想再吃时（即还没吃），发现只有 1 个桃子了。问题：最初共多少个桃子？
思路分析 逆推
1. day = 10 时 有 1 个桃子
2. day = 9 时 有 (day10 + 1) * 2 = 4
3. day = 8 时 有 (day9 + 1) * 2 = 10
4. 规律就是 前一天的桃子 = (后一天的桃子 + 1) *2//就是我们的能力
5. 递归
*/
    public int peach(int day) {
        if(day == 10) {//第 10 天，只有 1 个桃
        return 1;
        } else if ( day >= 1 && day <=9 ) {
        return (peach(day + 1) + 1) * 2;//规则，自己要想
        } else {
        System.out.println("day 在 1-10");
        return -1;
        }
    }
}
```

## 拓展（较难）
[走迷宫问题](https://www.bilibili.com/video/BV1fh411y7R8?t=2.0&p=222)
[汉诺塔问题](https://www.bilibili.com/video/BV1fh411y7R8?t=1.0&p=226)
[八皇后问题](https://www.bilibili.com/video/BV1fh411y7R8?t=0.9&p=227)