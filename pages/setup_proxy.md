---
title: چگونه فیلترشکن رایگان راه اندازی کنیم
nav: راه اندازی فیلترشکن اختصاصی رایگان
nav_order: 1
---

در این مقاله به شما آموزش میدهیم چگونه یک فیلترشکن اختصاصی ایجاد کنید.


## ایده کلی
شرکت هایی مثل مایکروسافت و دیجیتال اوشن برای دانشجوها حدود 100 دلار کردیت یکساله رایگان (قابل تمدید) ارائه میکنند

ما از این کردیت رایگان استفاده میکنیم تا دو پروکسی برای خانواده خود ایجاد کنیم

- یک پروکسی برای تلگرام
- یک پروکسی برای عبور از فیلتر سایر اپلیکیشن ها و برنامه ها

## مراحل
### مرحله 1: ایجاد یک اکانت دانشجویی در مایکروسافت azure


ابتدا وارد سایت [Microsoft Azure](https://azure.microsoft.com/en-us/free/students/) شوید
و مراحل زیر را مطابق گیف زیر انجام دهید:

{% include figure.html img="http://hiddify.github.io/assets/create_student_account.gif" alt="create student account in azure" caption="How to create student account in azure" %}


برای مشاهده میزان اعتبار باقیمانده در حساب کاربری خود از لینک زیر اقدام کنید
[مشاهده اعتبار دانشجویی در azure](https://www.microsoftazuresponsorships.com/Balance)

### مرحله 2: ساخت یک ماشین مجازی در azure برای تلگرام
بر روی این 
[لینک](https://portal.azure.com/)
  کلیک کنید و مراحل را مطابق گیف زیر ادامه دهید.

در این گیف یک مقدار کد نیاز است که از زیر آن را کپی کنید
```
#cloud-config
users:
  - default
  - name: tgproxy
package_upgrade: true
packages:
  - python3
  - python3-uvloop 
  - python3-cryptography
  - python3-socks 
  - libcap2-bin 
  - ca-certificates
  - curl
  - wget
  - gnupg-agent
  - software-properties-common
  - git
runcmd:
  # install docker following the guide: https://docs.docker.com/install/linux/docker-ce/ubuntu/
  - cd /opt/
  - git clone https://github.com/alexbers/mtprotoproxy 
  - cd  mtprotoproxy
  - sed -i 's/00000000000000000000000000000001/751F2F753854422EA4C5FDDB8314F068/g' config.py
  - echo 'TLS_DOMAIN = "google.com"'>> config.py
  - wget https://raw.githubusercontent.com/hiddify/config/main/mtproxy.service
  - sudo mv mtproxy.service /etc/systemd/system/
  - sudo systemctl enable mtproxy.service
  - sudo systemctl start mtproxy.service
power_state:
  mode: reboot
  message: Restarting after installing
```
{% include figure.html img="http://hiddify.github.io/assets/create-vm.gif" alt="create vm in azure" caption="How to create a vm in azure" %}

پس از کپی کردن ip ارائه شده آن را به جای ip در لینک زیر قرار دهید و از پروکسی تلگرام اختصاصی لذت ببرید

```
https://t.me/proxy?server=ip&port=443&secret=ee751F2F753854422EA4C5FDDB8314F068676f6f676c652e636f6d
```

### مرحله 2: ساخت یک ماشین مجازی در azure برای پروکسی سایت ها و اپلیکیشن ها
بر روی این 
[لینک](https://portal.azure.com/)
  کلیک کنید و مراحل را مطابق گیف زیر ادامه دهید.
 در گیف زیر به جای telegram عبارت gost را قرار دهید

در این گیف یک مقدار کد نیاز است که از زیر آن را کپی کنید
```
#cloud-config
groups:
  - gost
users:
  - default
package_upgrade: true
packages:
  - apt-transport-https
  - ca-certificates
  - curl
  - wget
  - gnupg-agent
  - software-properties-common
  - git
runcmd:
  - mkdir -p /opt/gost; cd /opt/gost
  - wget https://github.com/ginuerzh/gost/releases/download/v2.11.4/gost-linux-amd64-2.11.4.gz
  - gunzip gost*
  - mv gost* gost
  - chmod +x gost
  - wget https://raw.githubusercontent.com/hiddify/config/main/gost-systemd.service -O gost.service
  - sed -i 's/user:pass/751F2F753854422EA4C5FDDB8314F068:1/g' gost.service
  - sudo mv gost.service /etc/systemd/system/
  - sudo systemctl enable gost.service
  - sudo systemctl start gost.service
power_state:
  mode: reboot
  message: Restarting after installing docker & docker-compose
```
{% include figure.html img="http://hiddify.github.io/assets/create-vm.gif" alt="create vm in azure" caption="How to create a vm in azure" %}

پس از کپی کردن ip ارائه شده آن را به جای ip در لینک زیر قرار دهید و از پروکسی اختصاصی لذت ببرید


```
mixed-port: 7890
allow-lan: false
log-level: info
secret: ""
external-controller: 127.0.0.1:9090
ipv6: false
mode: rule
proxies:
  - name: Proxy
    type: http
    server: ip
    port: "443"
    tls: true
    skip-cert-verify: true
    sni: google.com
    username: 751F2F753854422EA4C5FDDB8314F068
    password: 1

rule-providers:
  iran:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/hiddify/clash/main/iran.yml"
    path: ./ruleset/iran.yaml
    interval: 432000
rules:
  - RULE-SET,iran,DIRECT
  - DOMAIN,google.com,DIRECT
  - DST-PORT,80,Proxy
  - DST-PORT,443,Proxy
  - MATCH,DIRECT

```
این تنظیمات را کپی کنید و در کامپیوتر با نام `hiddify.yml`  ذخیره کنید 
و با استفاده از لینک زیر کلاینت مورد نظر را کانفیگ کنید

[آموزش استفاده از کلش](https://hiddify.github.io/how_to_use_clash.html)

<script src="{{ '/assets/change_secret.js' | relative_url }}"></script>
