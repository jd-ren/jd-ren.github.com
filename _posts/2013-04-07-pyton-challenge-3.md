---
layout: post
title: "python challenge 3"
description: ""
category: python
tags: [python, python challenge]
---
{% include JB/setup %}
[地址](http://www.pythonchallenge.com/pc/def/equality.html)  

第三题比较简单，主要是考察对re模块的使用

python代码
{% highlight python %}
import re

if __name__=='__main__'：
    f = open('3.txt', 'r')
    t = f.read()

    result = re.findall('[^A-Z][A-Z]{3}[a-z][A-Z]{3}[A-Z]', t)
    print ''.join(x[4:5] for x in result)
    
    f.close()
{% endhighlight %}
