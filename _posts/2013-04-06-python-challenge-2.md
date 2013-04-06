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
{% endhighlight %}
