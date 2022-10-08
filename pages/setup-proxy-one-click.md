---
title: چگونه با یک کلیک فیلترشکن خوب نصب کنیم
nav: راه اندازی فیلترشکن اختصاصی با یک کلیک
nav_order: 2
---

در این مقاله به شما آموزش میدهیم چگونه یک فیلترشکن اختصاصی ایجاد کنید.


# پیش نیازها:
- یک vps آماده با ubuntu 20.04 و آی پی مثلا `1.1.1.1`
- یک دامنه یا زیردامنه (برای مثال: `myservice.hiddify.com`)
## مرحله 1: تنظیم آی پی VPS در دامنه
یک رکورد A ایجاد کنید که به آی پی VPS (در مثال ما `1.1.1.1`) متصل باشد.
[آموزش CPANEL](https://my.mihanwebhost.com/knowledgebase.php?action=displayarticle&id=267)

### مرحله 2: اجرای اسکریپت
ابتدا دامنه خود را در 
<form class="form-inline">
  <div class="input-group mb-2 mr-sm-2">
    <div class="input-group-prepend">
      <div class="input-group-text">domain</div>
    </div>
    <input  type="text" class="form-control" id="userdomain" placeholder="domain" value="myservice.hiddify.com" oninput="handleValueChange()">
  </div>
</form>  

دستور زیر را اجرا کنید
```
wget https://github.com/hiddify/config/blob/main/shadowsocks-telegram/setup-ss-tg.sh
setup-ss-tg.sh 751F2F753854422EA4C5FDDB8314F068 myservice.hiddify.com
```
پس از اجرای موفقیت آمیز، سرور ری استارت میشود و با کلیک بر روی لینک زیر میتوانید جزییات کانفیگ سمت کلاینت سرور را ببینید:
<a href="https://myservice.hiddify.com/751F2F753854422EA4C5FDDB8314F068/" target='_blank' class='btn btn-primary'>تنظیمات اختصاصی برای کلاینت ها </a>
<div class="alert alert-success">
توجه داشته باشید که لینک را حتما کپی کنید. این لینک به صورت تصادفی ایجاد شده و با ریفرش شدن صفحه تغییر میکند  پس آن را در جای امنی ذخیره کنید
</div>


<script src="{{ '/assets/change_secret.js' | relative_url }}"></script>

<script>
  codes=document.getElementsByTagName('code');
  as=document.getElementsByTagName('a');
  default_contents={'code':{},'a':{}}
  for (i=0; i<codes.length;i++){
    default_contents['code'][i]=codes[i].innerHTML;
  }
  for (i=0; i<as.length;i++){
    default_contents['a'][i]={'href':as[i].href,'inner':as[i].innerHTML}
  }
function handleValueChange(){
  var host = document.getElementById("userdomain").value;
  for (i=0; i<codes.length;i++){
    //codes[i].innerHTML=codes[i].innerHTML.replaceAll('defaultusersecret',secret);
    codes[i].innerHTML=default_contents['code'][i].replaceAll('myservice.hiddify.com',host);
  }
  for (i=0; i<as.length;i++){
    //as[i].href=as[i].href.replaceAll('defaultusersecret',secret);
    as[i].href=default_contents['a'][i]['href'].replaceAll('myservice.hiddify.com',host);
    //as[i].innerHTML=as[i].innerHTML.replaceAll('defaultusersecret',secret);
    as[i].innerHTML=default_contents['a'][i]['inner'].replaceAll('myservice.hiddify.com',host);
  }
 }

</script>
