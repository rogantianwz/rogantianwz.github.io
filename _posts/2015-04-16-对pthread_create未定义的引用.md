---
layout: post
category: c 
tagline: ""
tags: [pthread]
---
{% include JB/setup %}
今天在使用C编写了一个多线程任务,在编译链接的时候报了一个"对pthread_create未定义的引用"错误,google了之后找除了问题,这里记录一下.

* 首先,编译多线程程序必须使用-pthread(老的系统需要使用-lpthread, [参考](http://chaoslawful.iteye.com/blog/568602))编译选项,因为pthread库不是Linux默认链接库,链接时必须指定使用libthread.a库, 例如 `gcc -pthread -o threadtest threadtest.c`.

* 其次,如果这个时候还是报此错误则表明gcc仍未找到libpthread.a的路径,因为不同的系统的默认查找路径以及libpthread.a的存放位置都会不同,所以需要明确告知gcc去哪里查找.

* 然后, 使用find在/usr/lib/目录下查找,最后发现其位于 `/usr/lib/x86_64-linux-gnu` ,就可以使用gcc的-L参数来指定了,如 `gcc -L/usr/lib/x86_64-linux-gnu -pthread -o threadtest threadtest.c` 即可以正确编译链接多线程代码了.
