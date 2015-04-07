---
layout: post
category: IDEA 
tagline: "idea tomcat"
tags: [idea, tomcat]
---
{% include JB/setup %}
### 问题
最近我的eclipse在ubuntu下debug代码的时候总是会吃掉我4-5G的内存,弄得我debug几次之后就得重启eclipse.鉴于此准备try以下idea,在安装完之后使用使用tomcat来debug代码的时候报错`intellij Artifact app: Server is not connected. Deploy is not available`

### 解决
最后发现是我在tomcat的启动脚本中设置过JAVA_OPT(jvm参数),而我的idea中tomcat的run配置里也添加了jvm参数导致的,注掉启动脚本的JAVA_OPT后就OK了.  

