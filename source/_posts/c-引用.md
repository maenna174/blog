---
title: c++ 引用
date: 2024-11-26 23:55:51
tags:
- C++
---
## 引用 
### 语法
在变量名前加上"&"符号
```c++  
int &ref = a //ref是a的引用
```  
引用本质上就是一个"别名"  
ref与a的地址相同，值与a相同  
ref的值变化，a的值同相样变化。  
▲引用必须初始化．
```C++
int &rref=keo ref; //引用的引用
```
(rref仍指向a)  
▲引用只能掷定一个变量  
▲引用的数据类型与他邦确定的数据类型一样
```C++
Const int zere =o;
const int &cref=zero;//正确
const int &cref=10;  //正确
```
**常量引用和的初始化要求要宽松很多**  
绑定指针的引用
```C++
int * ptr = &a;    //指针指向a的地址
int * &pref = ptr; //声明了一个整型指针的引用pref，并且把它初始化为ptr的引用
*pref =......;
```
没有指向引用的指针
