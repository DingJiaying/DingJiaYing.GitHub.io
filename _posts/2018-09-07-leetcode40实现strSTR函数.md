---
layout: post
title:   leetcode40： 实现strStr()
categories: leetcode
description: leetcode第四十题
keywords: 
---


## 题目

实现 strStr() 函数。
给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
示例 1:

```
输入: haystack = "hello", needle = "ll"
输出: 2
```

示例 2:

```
输入: haystack = "aaaaa", needle = "bba"
输出: -1
```

说明:
当 needle 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。
对于本题而言，当 needle 是空字符串时我们应当返回 0 。这与C语言的 strstr() 以及 Java的 indexOf() 定义相符。



## 思路

直接比较，遇到相同的就直接进行，遇到不同的，两个下标全部回归。递归完的标志是，模板数组已经到了最后。

## 代码



	package leetcode41;
	/*
	实现strStr()
	 */
	public class Main {
	    public static void main(String[] args) {
	        String haystack1 = "hello", needle1 = "ll";
	        String haystack2 = "aaaaa", needle2 = "bba";
	        System.out.println(strStr(haystack1, needle1));
	        System.out.println(strStr(haystack2, needle2));
	    }
	    public static int strStr(String haystack, String needle){
	        if (haystack.length() == 0 || needle.length() == 0){
	            return 0;
	        }
	        int i = 0;
	        int j = 0;
	        while(i<haystack.length() && j<needle.length()){
	            if (haystack.charAt(i) == needle.charAt(j)){
	                i++;
	                j++;
	            }
	            else{
	                i = i-j+1;
	                j = 0;
	            }
	        }
	        if (j==needle.length()){
	            return i-j;
	        }
	        else {
	            return -1;
	        }
	    }
	}
	

