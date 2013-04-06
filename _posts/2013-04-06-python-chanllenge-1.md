---
layout: post
title: "python chanllenge 1"
description: ""
category: python 
tags: [python, python challenge]
---
{% include JB/setup %}
####解题
首先解码文本
>g fmnc wms bgblr rpylqjyrc gr zw fylb. rfyrq ufyr amknsrcpq ypc dmp. bmgle gr
>gl zw fylb gq glcddgagclr ylb rfyrq ufw rfg'q rcvr gq qm jmle. sqgle qrpgle.kyicrpylq() gq pcamkkclbcb.
>lmu ynnjw ml rfc spj.  '

根据提示，解码方法为每个字母的ascii码加2.

首先想到的是用ord()和chr()解题。解码后的文本是：  
i hope you didnt translate it by hand. thats what computers are for. doing it 
in by hand is inefficient and that's why this text is so long. using string.maketrans() is recommended.
now apply on the url.'
 
提示对url解码。并推荐使用string.maketrans().

####python代码
    #！/usr/bin/env python
    # -*- coding: utf-8 -*-
    
    import string
    
    s="g fmnc wms bgblr rpylqjyrc gr zw fylb. rfyrq ufyr amknsrcpq ypc dmp. bmgle gr gl zw fylb gq glcddgagclr ylb rfyr'q ufw rfgq rcvr gq qm jmle. sqgle qrpgle.kyicrpylq() gq pcamkkclbcb. lmu ynnjw ml rfc spj."
    
    #解法1
    a=''
    for i in s:
        if 96 < ord(i) < 123:
            i=chr((ord(i)+2-ord('a'))%26+ord('a'))
        a += i 

    print a
    print ''.join(chr(ord(x) + 2) for x in 'map')

    #解法2
    table = string.maketrans(string.ascii_lowercase,
            string.ascii_lowercase[2:] + string.ascii_lowercase[0:2])
    print s.translate(table)
    print 'map'.translate(table)

