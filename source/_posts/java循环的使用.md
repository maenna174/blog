---
title: java循环的使用
date: 2024-11-22 13:44:11
tags:
- Java
---
## switch
switch使用的基本语法
```java
switch（表达式）{ 
    case常量1:  //当.......
    语句块1;
    break;
    case 常量2;
    语句块2;
    break;
    ...
    case 常量n;
    语句块n;
    break;
    default:
        default语句块;
    break;
}
```
请编写一个程序，该程序可以接收一个字符，比如:a,b,c,d,e,f,g
a 表示星期一，b 表示星期二 …
根据用户的输入显示相应的信息.要求使用 switch 语句完成
思路分析
1. 接收一个字符 , 创建 Scanner 对象
2. 使用 switch 来完成匹配,并输出对应信息
代码

```java
import java.util.Scanner;
public class Switch01 {
//编写一个 main 方法
public static void main(String[] args) {

Scanner myScanner = new Scanner(System.in);
System.out.println("请输入一个字符(a-g)");
char c1 = myScanner.next().charAt(0);//
//在 java 中，只要是有值返回，就是一个表达式
    switch(c1) {
        case 'a' :
        System.out.println("今天星期一,猴子穿新衣");
        break;
        case 'b' :
        System.out.println("今天星期二,猴子当小二");
        break;
        case 'c' :
        System.out.println("今天星期三,猴子爬雪山..");
        break;
        //..... default:
        System.out.println("你输入的字符不正确，没有匹配的");
    }
    System.out.println("退出了 switch ,继续执行程序");
    }
}
```
### 注意事项
1. 表达式数据类型，应和case后的常量类型一致，或者是可以自动转成可以相互比较的
类型，比如输入的是学符，而常量是int
2. switch(表达式)中表达式的返回值必须是：(byte,short,int,charenum[救
举.String)
3. case子句中的值必须是常量，而不能是变量
4. default子句是可选的，当没有匹配的case时，执行default
5. break语句用来在执行完一个case分支后使程序跳出switch语句块；如果没有写
break,程序会顺序执行到switch结尾，除非遇到break;
### switch和if的比较
1. 如果判断的具体数值不多，而且符合byte、short、int、char,enum[枚举],String这6种类型。虽然两个语句都可以使用，建议使用swtich语句。
2. 其他情况：对区间判断，对结果为boolean类型判断，使用if，if的使用范围更广

## for循环控制
### 基本语法
```java
for(循环变量初始化；循环条件；循环变量迭代){
    循环操作(可以多条语句);
}
```
### 说明
1. for关键字，表示循环控制
2. for有四要素:(1)循环变量初始化(2)循环条件(3)循环操作(4)循环变量迭代
3. 循环操作,这里可以有多条语句，也就是我们要循环执行的代码
4. 如果循环操作(语句)只有一条语句，可以省略{},

### 注意事项和细节说明
1. 循环条件是返回一个布尔值的表达式
2. for(;循环判断条件;)中的初始化和变量迭代可以写到其它地方，但是两边的分号不能省略。
3. 循环初始值可以有多条初始化语句，但要求类型一样，并且中间用逗号隔开，循环变量迭代也可以有多条变量迭代语句，中间用逗号隔开。

### 例题
打印 1~100 之间所有是 9 的倍数的整数，统计个数及总和.
```java
public class ForExercise {
    //编写一个 main 方法
    public static void main(String[] args) {
    //打印 1~100 之间所有是 9 的倍数的整数，统计个数 及 总和.[化繁为简,先死后活]
    //老韩的两个编程思想(技巧)
    //1. 化繁为简 : 即将复杂的需求，拆解成简单的需求，逐步完成 编程 = 思想 --练习-> 代码
    //2. 先死后活 : 先考虑固定的值，然后转成可以灵活变化的值
    //
    //思路分析
    //打印 1~100 之间所有是 9 的倍数的整数，统计个数 及 总和
    //化繁为简
    //(1) 完成 输出 1-100 的值
    //(2) 在输出的过程中，进行过滤，只输出 9 的倍数 i % 9 ==0
    //(3) 统计个数 定义一个变量 int count = 0; 当 条件满足时 count++;
    //(4) 总和 , 定义一个变量 int sum = 0; 当条件满足时累积 sum += i;
    //先死后活
    //(1) 为了适应更好的需求，把范围的开始的值和结束的值，做出变量
    //(2) 还可以更进一步 9 倍数也做成变量 int t = 9;
    int count = 0; //统计 9 的倍数个数 变量
    int sum = 0; //总和
    int start = 10;
    int end = 200;
    int t = 5; // 倍数
    for(int i = start; i <= end; i++) {
        if( i % t == 0) {
            System.out.println("i=" + i);
            count++;
            sum += i;//累积
        }
    }
    System.out.println("count=" + count);
    System.out.println("sum=" + sum);
    }
}
```
## while循环控制
### 基本语法
循环变量初始化
```java
while(循环条件){
    循环体(语句)；
    循环变量迭代；
}
```
### 说明
1. while循环也有四要素
2. 只是四要素放的位置和for不一样

### 注意事项和细节说明
1. 循环条件是返回一个布尔值的表达式  
2. while循环是先判断再执行语句

## do..while 循环控制
### 基本语法
```java
循环变量初始化;
do{
    循环体(语句);
    循环变量迭代;
}while(循环条件);
```
### 说明
1. do while 是关键字
1. 也有循环四要素, 只是位置不一样
2. 先执行，再判断，也就是说，一定会至少执行一次
3. 最后 有一个 分号 ;

### 注意事项和细节说明
1. 循环条件是返回一个布尔值的表达式
2. do..while 循环是先执行，再判断， 因此它至少执行一次