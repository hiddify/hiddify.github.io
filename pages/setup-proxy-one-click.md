---
title: چگونه با یک کلیک فیلترشکن خوب نصب کنیم
nav: راه اندازی فیلترشکن اختصاصی با یک کلیک
nav_order: 2
---

در این مقاله به شما آموزش میدهیم چگونه یک فیلترشکن اختصاصی ایجاد کنید.


# پیش نیازها:
- یک vps آماده با ubuntu 20.04 و آی پی مثلا `1.1.1.1`
- یک دامنه یا زیردامنه (برای مثال: `myservice.hiddify.com`) که رکورد A ی آن به آی پی شما وصل باشد. اگر زیر دامنه ندارید از 
 [این لینک](create-subdomain.html)
یک زیر دامنه برای خود بسازید

### مرحله 1: پارامترها
ابتدا دامنه خود را در 
<form class="form-inline">
  <div class="input-group mb-2 mr-sm-2">
    <div class="input-group-prepend">
      <div class="input-group-text">domain</div>
    </div>
    <input  type="text" class="form-control" id="userdomain" placeholder="domain" value="myservice.hiddify.com" oninput="handleValueChange()">
  </div>
</form>  
قرار دهید.

### مرحله 2: چک کردن آنکه این زیر دامنه به آی پی متصل است 

<a href="https://mxtoolbox.com/SuperTool.aspx?action=a%3amyservice.hiddify.com&run=toolpage" class="btn btn-primary">check</a>
اگر تازه انجام داده اید و در بالا نمیبینید 5 دقیقه صبر کنید و مجدد تست کنید
  
### مرحله 3: اجرای اسکریپت


دستور زیر را اجرا کنید
```
wget https://raw.githubusercontent.com/hiddify/config/main/install.sh
bash install.sh 751F2F753854422EA4C5FDDB8314F068 myservice.hiddify.com
```
پس از اجرای موفقیت آمیز، سرور ری استارت میشود و با کلیک بر روی لینک زیر میتوانید جزییات کانفیگ سمت کلاینت سرور را ببینید:
<a href="https://myservice.hiddify.com/751F2F753854422EA4C5FDDB8314F068/" target='_blank' class='btn btn-primary'>تنظیمات اختصاصی برای کلاینت ها </a>
<div class="alert alert-success">
توجه داشته باشید که لینک را حتما کپی کنید. این لینک به صورت تصادفی ایجاد شده و با ریفرش شدن صفحه تغییر میکند  پس آن را در جای امنی ذخیره کنید
</div>


# تنظیمات پیشرفته

اگر کار باCDN را آشنایی دارید، کافی است که بر روی دامنه پروکسی را تنظیم کنید
<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        توضیحات پیشرفته
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
      <div class="accordion-body">
       
برگرفته از دوستان[FreeInternet](https://github.com/WeAreMahsaAmini/FreeInternet/tree/main/protocols/shadowsocks-v2ray-tls)

### 2. Arvancloud setup

4. Log in to the Arvancloud account and add your domain.

```
Domain List > Add new domains
```

![Arvancloud dashboard > Add new domain](https://github.com/WeAreMahsaAmini/FreeInternet/tree/main/protocols/media/arvanclound_adddomain.jpg 'Click on Add new domain')

Then:

- Enter your domain name
- Select Free plan
- Skip DNS Records
- Note the nameservers presented on the last step

![Add new domain > Nameservers](https://github.com/WeAreMahsaAmini/FreeInternet/tree/main/protocols/media/arvanclound_nameservers.jpg 'Copy these nameservers')

- Go to your domain registrar (the website where you bought your domain, e.g. Godaddy, Namecheap, ...)
- Update the nameservers to the one you got in Arvancloud (after adding the domain).

After your domain nameservers changed successfully (depending on the registrar, it can take a few hours, but it's usually quite fast), your domain is now using Arvancloud DNS.

5. Connect your domain to your server's IP address using `A` records. Make sure the `Cloud Service` option is enabled for each record.
   ![Add new domain > Nameservers](https://github.com/WeAreMahsaAmini/FreeInternet/tree/main/protocols/media/arvanclound_add_dns.jpg 'Enable cloud services')

6. Go to `HTTPS settings` on the navbar, select `Issue certificate`. It will take around 30 minutes for the certificate to be ready.

7. After the certificate is issued, enable the `Activate HTTPS` option.
   ![HTTPS Settings > Activate HTTPS](https://github.com/WeAreMahsaAmini/FreeInternet/tree/main/protocols/media/arvanclound_https.jpg 'Enable cloud services')
      </div>
    </div>
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
