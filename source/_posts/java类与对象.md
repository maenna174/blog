---
title: java类与对象
date: 2024-11-22 00:41:06
tags:
- java
---
# 类，对象
## 什么是类，对象
1. 类是抽象的，概念的，代表一类事物，比如人类，猫类．.，即它是数据类型
2. 对象是具体的，实际的，代表一个具体事物，即是实例
3. 类是对象的模板，对象是类的一个个体，对应一个实例

## 举例
```java
new cat（）创建一只猫（猫对象）  
cat cat1 = new cat（）把创建的猫赋值给 cat1  
cat1 就是一个对象

class Cat          //属性/成员变量
    {  
    String name;   //名字  
    int age;       //年龄  
    String color;  //颜色  
    double weight; //体重
    }

Cat cat = new Cat()  
cat.name="小白";  
cat.age=12;  
cat.color="白色";
```
![](https://free4.yunpng.top/2024/11/22/67408335ba89f.png)

## tips
1. 从概念或叫法上看： 成员变量 = 属性 = field （字段）（即 成员变量是用来表示属性的，授课中，统一叫属性）  
案例演示：Car(name,price,color)  
2. 属性是类的一个组成部分，一般是基本数据类型，也可是引用类型（对象，数组）。比如我们前面定义猫类 的 int age 就是属性
3. 属性的定义语法同变量，示例：访问修饰符 属性类型 属性名；
访问修饰符： 控制属性的访问范围
 有四种访问修饰符 public, proctected, 默认， private
4. 属性的定义类型可以为任意类型，包含基本类型或引用类型
5. 属性如果不赋值，有默认值，规则和数组一致。具体说：int 0,short 0,byte 0, long 0, float 0.0,double 0.0, char \u0000, boolean false,String null

## 如何创建对象
1. 先声明再创建
```java
Cat cat ;
cat = new Cat（）;
```
2. 直接创建  
```java
Cat cat = new Cat();
```

## 类和对象的内存分配机制
Java内存的结构分析  
1. 栈： 一般存放基本数据类型（局部变量）
2. 堆：存放对象（Cat cat，数组等）
3. 方法区：常量池（常量，比如字符串），类加载信息  
4. 示意图［Cat (name, age, price)]

## Java创建对象的流程简单分析
```java
Person p = new Person();
p.name= "jack" ;
p.age = 10
```
1. 先加载Person类信息（属性和方法信息，只会加载一次）
2. 在堆中分配空间进行默认初始化（看规则）
3. 把地址赋给p,p就指向对象
4. 进行指定初始化，比如
```java 
p.name = " jack" : p.age = 10
```

## 方法（成员方法）
添加speak 成员方法，输出"我是一个好人"
解读
1. public 表示方法是公开
2. void：表示方法没有返回值
3. speak():speak是方法名，(）形参列表
4.{｝方法体，可以写我们要执行的代码
5. System.out.println("我是一个好人")；
表示我们的方法就是输出一句话


## 添加getSum成员方法，计算两个数的和
1. public 表示方法是公开的
2. int ：表示方法执行后，返回一个 int 值
3. getSum 方法名
4. （int num1, int num2）形参列表，2个形参，可以接收用户传入的两个数
5. return res; 表示把 res 的值， 返回

```java
public int getSum(int num1, int num2) {
int res = num1 + num2;
return res;
```
## 成员方法快速入门
1) 添加 speak 成员方法,输出 “我是一个好人”   
2) 添加 cal01 成员方法,可以计算从 1+..+1000 的结果
3) 添加 cal02 成员方法,该方法可以接收一个数 n，计算从 1+..+n 的结果
4) 添加 getSum 成员方法,可以计算两个数的和代码

```java
public class Method01 {
//编写一个 main 方法
public static void main(String[] args) {
    //方法使用
    //1. 方法写好后，如果不去调用(使用)，不会输出
    //2. 先创建对象 ,然后调用方法即可
    Person p1 = new Person();
    p1.speak(); //调用方法
    p1.cal01(); //调用 cal01 方法
    p1.cal02(5); //调用 cal02 方法，同时给 n = 5
    p1.cal02(10); //调用 cal02 方法，同时给 n = 10
    //调用 getSum 方法，同时 num1=10, num2=20
    第 194页
    韩顺平循序渐进学 Java 零基础
    //把 方法 getSum 返回的值，赋给 变量 returnRes
    int returnRes = p1.getSum(10, 20);
    System.out.println("getSum 方法返回的值=" + returnRes);
    }
}
class Person {
    String name;
    int age;
    //方法(成员方法)
    //添加 speak 成员方法,输出 “我是一个好人”
    //解读
    //1. public 表示方法是公开
    //2. void ： 表示方法没有返回值
    //3. speak() : speak 是方法名， () 形参列表
    //4. {} 方法体，可以写我们要执行的代码
    //5. System.out.println("我是一个好人"); 表示我们的方法就是输出一句话
    public void speak() {
        System.out.println("我是一个好人");
    }
    //添加 cal01 成员方法,可以计算从 1+..+1000 的结果
    public void cal01() {
        //循环完成
        int res = 0;
        for(int i = 1; i <= 1000; i++) {
            res += i;
        }
    System.out.println("cal01 方法 计算结果=" + res);
    }
    //添加 cal02 成员方法,该方法可以接收一个数 n，计算从 1+..+n 的结果
    //解读
    //1. (int n) 形参列表， 表示当前有一个形参 n, 可以接收用户输入
    public void cal02(int n) {
    //循环完成
        int res = 0;
        for(int i = 1; i <= n; i++) {
            res += i;
        }
    System.out.println("cal02 方法 计算结果=" + res);
    }
    //添加 getSum 成员方法,可以计算两个数的和
    //解读
    //1. public 表示方法是公开的
    //2. int :表示方法执行后，返回一个 int 值
    //3. getSum 方法名
    //4. (int num1, int num2) 形参列表，2 个形参，可以接收用户传入的两个数
    //5. return res; 表示把 res 的值， 返回
    public int getSum(int num1, int num2) {
        int res = num1 + num2;
        return res;
    }
}
```
## 方法的调用机制原理
![](https://free4.yunpng.top/2024/12/04/674f35630f13f.png)
[详细视频讲解](https://www.bilibili.com/video/BV1fh411y7R8?t=1013.7&p=204)

## 成员方法的好处
1) 提高代码的复用性
2) 可以将实现的细节封装起来，然后供其他用户来调用即可

## 成员方法的定义
```java
访问修饰符 返回数据类型 方法名（形参列表..） {//方法体
    语句；
return 返回值;
}
```
1) 形参列表：表示成员方法输入 cal(int n) ， getSum(int num1, int num2)
2) 返回数据类型：表示成员方法输出, void 表示没有返回值
3) 方法主体：表示为了实现某一功能代码块
4) return 语句不是必须的。  

## 注意事项和使用细节
[视频](https://www.bilibili.com/video/BV1fh411y7R8?t=2.3&p=207)
### 访问修饰符 (作用是控制 方法使用的范围)
如果不写默认访问，[有四种: public, protected, 默认, private], 具体在后面说
### 返回数据类型
1) 一个方法最多有一个返回值 [思考，如何返回多个结果 返回数组 ]
2) 返回类型可以为任意类型，包含基本类型或引用类型(数组，对象)
3) 如果方法要求有返回数据类型，则方法体中最后的执行语句必须为 return 值; 而且要求返回值类型必须和 return 的
值类型一致或兼容
4) 如果方法是 void，则方法体中可以没有 return 语句，或者 只写 return ;
### 形参列表
1.一个方法可以有0个参数,也可以有多个参数,中间用逗号隔开,比如getSum(intn1,intn2)
2.参数类型可以为任意类型,包含基本类型或用类型,比如printArr(intDDmap)
3.调用带参数的方法时,一定对应着参数列表传入相同类型或兼容类型的参数!(getSum】
4.方法定义时的参数称为形式参数,简称形参;方法调用时的传入参数称为实际参数,简称实参
实参和形参的类型要一致或兼容、个数、顺序必须一致![演示]
### 方法体
里面写完成功能的具体的语句,可以为输入、输出、变量、运算、分支、循环、方法调用,但里
面不能再定义方法!  
   
**实例如下**
```java
public class MethodDetail {
    public static void main(String[] args) {
        AA a = new AA();
        int[] res = a.getSumAndSub(1, 4);
        System.out.println("和=" + res[0]);
        System.out.println("差=" + res[1]);
        //细节: 调用带参数的方法时，一定对应着参数列表传入相同类型或兼容类型 的参数
        byte b1 = 1;
        byte b2 = 2;
        a.getSumAndSub(b1, b2);//byte -> int
        //a.getSumAndSub(1.1, 1.8);//double ->int(×)
        //细节: 实参和形参的类型要一致或兼容、个数、顺序必须一致
        //a.getSumAndSub(100);//× 个数不一致
        a.f3("tom", 10); //ok
        //a.f3(100, "jack"); // 实际参数和形式参数顺序不对
        }
    }
    class AA {
        //细节: 方法不能嵌套定义
        public void f4() {
        //错误
        // public void f5() {
        // }
    }
    public void f3(String str, int n) {
        }
    //1. 一个方法最多有一个返回值 [思考，如何返回多个结果 返回数组 ]
    public int[] getSumAndSub(int n1, int n2) {
        int[] resArr = new int[2]; //
        resArr[0] = n1 + n2;
        resArr[1] = n1 - n2;
        return resArr;
    }
    //2. 返回类型可以为任意类型，包含基本类型或引用类型(数组，对象)
    // 具体看 getSumAndSub
    //
    //3. 如果方法要求有返回数据类型，则方法体中最后的执行语句必须为 return 值;
    // 而且要求返回值类型必须和 return 的值类型一致或兼容
    public double f1() {
        double d1 = 1.1 * 3;
        int n = 100;
        return n; // int ->double
        //return d1; //ok? double -> int
    }
    //如果方法是 void，则方法体中可以没有 return 语句，或者 只写 return ;
    //老韩提示：在实际工作中，我们的方法都是为了完成某个功能，所以方法名要有一定含义
    //，最好是见名知意
    public void f2() {
    System.out.println("hello1");
    System.out.println("hello1");
    System.out.println("hello1");
    int n = 10;
    //return ;
    }
}
```
## 方法调用细节说明()
1. 同一个类中的方法调用:直接调用即可。比如print(参数)
案例演示:A类sayOk调用print0
2. 跨类中的方法A类调用B类方法:需要通过对象名调用。比如对象名.方法名(参
数);案例演示:B类sayHello调用print0
3. 特别说明一下:跨类的方法调用和方法的访问修饰符相关    

**实例如下**
```java
public class MethodDetail02 {
    //编写一个 main 方法
    public static void main(String[] args) {
    A a = new A();
    //a.sayOk();
    a.m1();
    }
}
class A {
        //同一个类中的方法调用：直接调用即可
        //
    public void print(int n) {
        System.out.println("print()方法被调用 n=" + n);
    }
    public void sayOk() { //sayOk 调用 print(直接调用即可)
        print(10);
        System.out.println("继续执行 sayOK()~~~");
    }
    //跨类中的方法 A 类调用 B 类方法：需要通过对象名调用
    public void m1() {
    //创建 B 对象, 然后在调用方法即可
        System.out.println("m1() 方法被调用");
        B b = new B();
        b.hi();
        System.out.println("m1() 继续执行:)");
    }
}
class B {
    public void hi() {
        System.out.println("B 类中的 hi()被执行");
    }
}
```

