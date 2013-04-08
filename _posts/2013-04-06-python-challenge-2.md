---
layout: post
title: "python challenge 2"
description: ""
category: python
tags: [python, python challenge]
---
{% include JB/setup %}
[地址](http://www.pythonchallenge.com/pc/def/ocr.html)
#####解题
根据提示， 打开网页源代码。看到题目：find rare characters in the mess below:
题目比较简单，不过网上的大部分答案都是直接在文本找出现的字母。
#####python代码
{% highlight python %}
import collections
import re
import string

f = open('2.txt', 'r')
t = f.read()

#方法1
a = ''
for i in t:
    if 96 < ord(i) < 123:# if i in string.letters
        a += i
print a

#方法2
print re.findall('[a-z]', t)

#方法3， 使用Counter统计

c = collections.Counter(t)
print c.most_common()

"""方法4.刚在学习字符串时，觉得可以利用字符串对象的
内建方法count完成方法3.代码比方法3多了点，不过百分百
原创：）。第一个循环统计文本里的不同字符，第二个循环
统计各字符数量。4.8
"""
a = ''
for i in t:
    if i in a:
        pass
    else:
        a += i
for i in a:
    print i, t.count(i)
{% endhighlight %}
