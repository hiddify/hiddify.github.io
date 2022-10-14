---
title: فیلترشکن چندگانه
nav: فیلترشکن + تلگرام با یک کلیک
nav_order: 1
---

در این مقاله به شما آموزش میدهیم چگونه یک فیلترشکن اختصاصی مالتی پروتوکل در پورت 443 ایجاد کنید.
موارد پشتیبانی شده
- Telegram Proxy
- Signal Proxy
- Shadowsocks+obfs
- Shadowsocks+v2ray
- DNS over HTTPS
- Automatic use proxy for non-Iranian sites

همچنین سعی شده تا جلوی کشف پروکسی نیز توسط فیلترچی گرفته شود

# پیش نیازها:
- یک vps آماده با ubuntu 20.04 و آی پی مثلا `1.1.1.1`
- یک دامنه یا زیردامنه (برای مثال: `myservice.hiddify.com`) که رکورد A ی آن به آی پی شما وصل باشد. اگر زیر دامنه ندارید از 
 [این لینک](create-subdomain.html)
یک زیر دامنه برای خود بسازید

### مرحله 1: پارامترها
ابتدا دامنه خود را در بخش زیر قرار دهید. 
<form class="form-inline">
  <div class="input-group mb-2 mr-sm-2">
    <div class="input-group-prepend">
      <div class="input-group-text">domain</div>
    </div>
    <input  type="text" class="form-control" id="userdomain" placeholder="domain" value="myservice.hiddify.com" oninput="handleValueChange()">
  </div>
</form>  
<form class="form-inline">
  <div class="input-group mb-2 mr-sm-2">
    <div class="input-group-prepend">
      <div class="input-group-text">secret</div>
    </div>
    <input  type="text" class="form-control" id="usersecret" placeholder="secret" pattern="[0-9a-fA-F]{32}" required minlength="32" maxlength="32"  value="751F2F753854422EA4C5FDDB8314F068" oninput="handleValueChange()">
  </div>
</form>  


### مرحله 2: چک کردن آنکه این زیر دامنه به آی پی متصل است 
با کلیک بر روی دکمه 
<a href="https://mxtoolbox.com/SuperTool.aspx?action=a%3amyservice.hiddify.com&run=toolpage" class="btn btn-primary">check</a>
چک کنید که زیر دامنه درست به IP اشاره میکند.
اگر تازه انجام داده اید و در بالا IP سرور خود را نمی بینید 5 دقیقه صبر کنید و مجدد تست کنید

  
### مرحله 3: اجرای اسکریپت


دستور زیر را اجرا کنید
```
wget https://raw.githubusercontent.com/hiddify/config/main/install.sh
bash install.sh 751F2F753854422EA4C5FDDB8314F068 myservice.hiddify.com all myservice.hiddify.com
```
پس از اجرای موفقیت آمیز، سرور ری استارت میشود و با کلیک بر روی لینک زیر میتوانید جزییات کانفیگ سمت کلاینت سرور را ببینید:
<a href="https://myservice.hiddify.com/751F2F753854422EA4C5FDDB8314F068/" target='_blank' class='btn btn-primary'>تنظیمات اختصاصی برای کلاینت ها </a>
<div class="alert alert-success">
توجه داشته باشید که لینک را حتما کپی کنید. این لینک به صورت تصادفی ایجاد شده و با ریفرش شدن صفحه تغییر میکند  پس آن را در جای امنی ذخیره کنید
</div>


# تنظیمات پیشرفته

<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        توضیحات پیشرفته
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
      <div class="accordion-body">

       
       
برای سرعت بالاتر و گذر از اینترانت کافی است که یک دامنه خریداری کنید (برای مثال از اینجا به قیمت 1 دلار) 
سپس یک اکانت در ابرآروان ایجاد کنید میتوانید با یک شماره خارجی اینکار را انجام دهید
سپس nameserver بر روی دامنه ای که خریداری کرده اید را مطابق اعلامی ابرآروان پر کنید
سپس روی زیر دامنه دلخواه، آی پی سرور را تنظیم کنید و تیک کلود سرویس  را تنظیم کنید و سپس به جای <code>myservice.hiddify.com</code>  زیردامنه جدید خود را تنظیم کنید. لازم است این زیر دامنه با دامنه ای که در بالا انتخاب کرده اید متفاوت باشد.
       
       <br />
       سپس لینک زیر را با تغییر در نامه دامنه در مرورگر جهت مشاهده تنظیمات باز کنید.
       <br/>
       <code>
       https://myservice.hiddify.com/751F2F753854422EA4C5FDDB8314F068/
       </code>
       <br/>
       
       در زیر توضیحات با تصویر نشان داده شده است.
       
       
       
<article class="markdown-body entry-content container-lg" itemprop="text">




<h3 dir="auto"><a id="user-content-2-arvancloud-setup" class="anchor" aria-hidden="true" href="#2-arvancloud-setup"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2. Arvancloud setup</h3>
<ol start="4" dir="auto">
<li>Log in to the Arvancloud account and add your domain.</li>
</ol>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>Domain List &gt; Add new domains
</code></pre><div class="zeroclipboard-container position-absolute right-0 top-0">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn js-clipboard-copy m-2 p-0 tooltipped-no-delay" data-copy-feedback="Copied!" data-tooltip-direction="w" value="Domain List > Add new domains" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon m-2">
    <path fill-rule="evenodd" d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 010 1.5h-1.5a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-1.5a.75.75 0 011.5 0v1.5A1.75 1.75 0 019.25 16h-7.5A1.75 1.75 0 010 14.25v-7.5z"></path><path fill-rule="evenodd" d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0114.25 11h-7.5A1.75 1.75 0 015 9.25v-7.5zm1.75-.25a.25.25 0 00-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 00.25-.25v-7.5a.25.25 0 00-.25-.25h-7.5z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none m-2">
    <path fill-rule="evenodd" d="M13.78 4.22a.75.75 0 010 1.06l-7.25 7.25a.75.75 0 01-1.06 0L2.22 9.28a.75.75 0 011.06-1.06L6 10.94l6.72-6.72a.75.75 0 011.06 0z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media/arvanclound_adddomain.jpg"><img src="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media//arvanclound_adddomain.jpg" alt="Arvancloud dashboard > Add new domain" title="Click on Add new domain" style="max-width: 100%;"></a></p>
<p dir="auto">Then:</p>
<ul dir="auto">
<li>Enter your domain name</li>
<li>Select Free plan</li>
<li>Skip DNS Records</li>
<li>Note the nameservers presented on the last step</li>
</ul>
<p dir="auto"><a target="_blank" rel="noopener noreferrer" href="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media/arvanclound_nameservers.jpg"><img src="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media//arvanclound_nameservers.jpg" alt="Add new domain > Nameservers" title="Copy these nameservers" style="max-width: 100%;"></a></p>
<ul dir="auto">
<li>Go to your domain registrar (the website where you bought your domain, e.g. Godaddy, Namecheap, ...)</li>
<li>Update the nameservers to the one you got in Arvancloud (after adding the domain).</li>
</ul>
<p dir="auto">After your domain nameservers changed successfully (depending on the registrar, it can take a few hours, but it's usually quite fast), your domain is now using Arvancloud DNS.</p>
<ol start="5" dir="auto">
<li>
<p dir="auto">Connect your domain to your server's IP address using <code>A</code> records. Make sure the <code>Cloud Service</code> option is enabled for each record.
<a target="_blank" rel="noopener noreferrer" href="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media/arvanclound_add_dns.jpg"><img src="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media//arvanclound_add_dns.jpg" alt="Add new domain > Nameservers" title="Enable cloud services" style="max-width: 100%;"></a></p>
</li>
<li>
<p dir="auto">Go to <code>HTTPS settings</code> on the navbar, select <code>Issue certificate</code>. It will take around 30 minutes for the certificate to be ready.</p>
</li>
<li>
<p dir="auto">After the certificate is issued, enable the <code>Activate HTTPS</code> option.
<a target="_blank" rel="noopener noreferrer" href="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media/arvanclound_https.jpg"><img src="https://raw.githubusercontent.com/WeAreMahsaAmini/FreeInternet/main/protocols/media//arvanclound_https.jpg" alt="HTTPS Settings > Activate HTTPS" title="Enable cloud services" style="max-width: 100%;"></a></p>
</li>
</ol>










<a href="https://github.com/WeAreMahsaAmini/FreeInternet/tree/main/protocols/shadowsocks-v2ray-tls" >
       
برگرفته از دوستان FreeInternet
       </a>
</article>
      </div>
    </div>
  </div>





<script>
 const genRanHex = size => [...Array(size)]
  .map(() => Math.floor(Math.random() * 16).toString(16)).join('');
 document.getElementById("usersecret").value=genRanHex(32);
 
  codes=document.getElementsByTagName('code');
  as=document.getElementsByTagName('a');
  default_contents={'code':{},'a':{}}
 
 function replace_info(str){
  var host = document.getElementById("userdomain").value;
  var secret = document.getElementById("usersecret").value;
 
  str=str.replaceAll('myservice.hiddify.com',host);
  str=str.replaceAll('751F2F753854422EA4C5FDDB8314F068',secret);
  return str;
 }
 
  for (i=0; i<codes.length;i++){
    default_contents['code'][i]=codes[i].innerHTML;
  }
  for (i=0; i<as.length;i++){
    default_contents['a'][i]={'href':as[i].href,'inner':as[i].innerHTML}
  }
function handleValueChange(){
  for (i=0; i<codes.length;i++){
    codes[i].innerHTML=replace_info(default_contents['code'][i]);
  }
  for (i=0; i<as.length;i++){
    as[i].href=replace_info(default_contents['a'][i]['href']);
    as[i].innerHTML=replace_info(default_contents['a'][i]['inner']);
  }
 }

</script>
