---
layout: post
category: IDEA 
tagline: "idea"
tags: [idea]
---
{% include JB/setup %}
### 问题
我在shell中使用`./idea.sh`启动idea的时候提示在classpath中找不到tools.jar,建议我将`JAVA_HOME`设置为jdk的,而不要使用jre的,于是我去profile中配置了JAVA_HOME的路径,然后启动,OK  

但是当我通过在`/usr/share/applications/`中使用desktop-entry的方式启动的时候又报同样的错误,google到如下
>Actually the environment variables for Shell Session and Desktop GUI Session are different . If the error happens when you launch IntelliJ with Desktop Entry(the Launcher), you might don't have JAVA_HOME in your GUI Environment.

### 解决
由此了解到shell启动的环境变量和GUI启动的环境变量的不同,果断在idea.desktop中export JAVA_HOME, done!

### 参考
[这里](http://askubuntu.com/questions/275965/how-to-list-all-variables-names-and-their-current-values/356973#356973)有详尽的描述

