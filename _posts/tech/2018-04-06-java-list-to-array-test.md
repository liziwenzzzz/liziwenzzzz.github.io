---
layout: post
title: Java List to Array
category: 技术
tags: Java
keywords: 'List,Array'
published: true
---


分为两种情况，引用类型或者基本数据类型。
引用类型可以直接调用Java函数，基本数据类型需要一个一个的赋值。

$$ \alpha $$ 
$ a $

### 引用类型
Either:

    Foo[] array = list.toArray(new Foo[list.size()]);
    或者Foo[] array = list.toArray(new Foo[0]);
    若是：Foo[] array = list.toArray()则返回Object[]

or:

    Foo[] array = new Foo[list.size()];
    list.toArray(array); // fill the array
    
### 基本数据类型

    List<Integer> list = ...;
    int[] array = new int[list.size()];
    for(int i = 0; i < list.size(); i++) 
        array[i] = list.get(i);
        
## Array to List
    String[] s = new String[]{"A", "B", "C", "D","E"};
    List<String> list = Arrays.asList(s);
    注意：此处的list中的元素就是数组中的元素的引用，
    对数组的改变会影响list元素的值。
    因此这个转换只能用于引用类型。
