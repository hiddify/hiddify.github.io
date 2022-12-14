---
title: آموزش استفاده
layout: no_header
---

<h1>
لطفا از دارنده سرور بخواهید سرور را ارتقا دهد. این نسخه به زودی غیرفعال میگردد.
  https://github.com/hiddify/hiddify-config
</h1>
<details><summary>کانفیگ قبلی که ممکن است کار نکند</summary>

# پروکسی تلگرام
پروکسی تلگرام در همه سرورها فعال نیست. در صورتی که در این سرور فعال باشد، بر روی لینک زیر کلیک کنید تا بر روی تلگرام شما تنظیم شود.
<a href="tg://proxy?server=defaultserverhost&port=443&secret=eedefaultusersecret6d61696c2e676f6f676c652e636f6d" class='btn btn-primary'>پروکسی تلگرام کلیک کنید</a>


# پروکسی سایت ها و اپلیکشن ها:


<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
        اندروید - Android  - روش پیشنهادی
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        ابتدا یکی از نرم افزارهای زیر را دانلود کنید:
<a href="https://play.google.com/store/apps/details?id=com.github.kr328.clash"><img src="/images/google-play-badge.png"></a>
<a href="../gh/Kr328/ClashForAndroid/releases/download/v2.5.11/cfa-2.5.11-premium-universal-release.apk"><img src="/images/android-apk-badge.png"></a>


        
        <h2>لینک تنظیمات:</h2>
روی یکی از لینک های زیر با توجه به نیازتان **راست کلیک** کرده و کپی کنید

        <h3> استفاده هوشمند از فیلترشکن فقط برای سایت های فیلتر و واتساپ و اینستاگرام</h3>

<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/lite-meta.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/lite-meta.yml" class="btn btn-success copylink">کپی لینک</a>

<h3>استفاده هوشمند از فیلترشکن فقط برای سایت های فیلتر</h3>
        
<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/lite.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/lite.yml" class="btn btn-success copylink">کپی لینک</a>

        <h3>
استفاده هوشمند از فیلترشکن فقط برای سایت های خارجی
        </h3>
<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/normal.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/normal.yml" class="btn btn-success copylink">کپی لینک</a>


        <h3>
استفاده از فیلترشکن همیشه (کاهش سرعت سایت های داخلی)
        </h3>
<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/all.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/all.yml" class="btn btn-success copylink">کپی لینک</a>

<h2> کار با کلش اندروید
        </h2>
  
   چنانچه بر روی دکمه "نصب با یک کلیک" کلیک کرده اید دیگر نیاز به انجام مرحله اول تا پنچک را ندارید

        <div class="alert alert-danger">
        چنانچه با خطای Handshake مواجه شدید، لازم است که ابتدا از طریق روش دوم که در پایین این بخش هست استفاده کنید و سپس ادامه مراحل اینجا را طی کنید.
          
        </div>
        ابندا یکی از لینک تنظیمات کلش را کپی کنید و در بخش 2 مرحله 4 قرار دهید و مراحل را مطابق گیف زیر انجام دهید
       
{% include figure.html img="clash_android.gif" alt="How to use clash for Android" caption="How to use clash for Android" %}

        
        
      </div>
    </div>
  </div>
  
  
  
  
    <div class="accordion-item">
    <h2 class="accordion-header" id="headingThree3">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree3" aria-expanded="false" aria-controls="collapseThree3">
        اندروید روش بکاپ - غیر پیشنهادی
      </button>
    </h2>
    <div id="collapseThree3" class="accordion-collapse collapse" aria-labelledby="headingThree3" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        
        ابتدا یکی از نرم افزارهای زیر را دانلود کنید:
        <a href="https://play.google.com/store/apps/details?id=io.nekohasekai.sagernet"><img src="/images/google-play-badge.png"></a>
<a href="../gh/SagerNet/SagerNet/releases/download/0.8.1-rc02/SN-0.8.1-rc02-arm64-v8a.apk"><img src="/images/android-apk-badge.png"></a>
        
                
        <h2>
        کار با پروکسی در اندروید روش 2
        </h2>
ابتدا  بر روی دکمه "نصب با یک کلیک" کلیک کنید و سپس پروکسی را انتخاب و اجرا نمایید. 

<a href="ss://chacha20-ietf-poly1305:defaultusersecret@defaultserverhost:443?plugin=obfs-local%3Bobfs%3Dtls%3Bobfs-host%3Dwww.google.com&udp-over-tcp=true#defaultserverhost" class="btn btn-primary">نصب با یک کلیک</a>
<a href="ss://chacha20-ietf-poly1305:defaultusersecret@defaultserverhost:443?plugin=obfs-local%3Bobfs%3Dtls%3Bobfs-host%3Dwww.google.com&udp-over-tcp=true#defaultserverhost" class="btn btn-success copylink">کپی لینک</a>
        
      </div>
    </div>
</div>
      
      
  
  
  
  
  
  
  
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingTwo">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
        ویندوز، macOS و لینوکس
      </button>
    </h2>
    <div id="collapseTwo" class="accordion-collapse collapse" aria-labelledby="headingTwo" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        ابتدا یکی از نرم افزار زیر را با توجه به سیستم عامل خود دانلود و نصب کنید:
        <a href="../gh/Fndroid/clash_for_windows_pkg/releases/download/0.20.4/Clash.for.Windows.Setup.0.20.4.exe"><img src="/images/BadgeWindows.png"></a>
   <a href="../gh/Fndroid/clash_for_windows_pkg/releases/download/0.20.4/Clash.for.Windows-0.20.4.dmg"><img src="/images/BadgeMacOS.png"></a>
           <a href="../gh/Fndroid/clash_for_windows_pkg/releases/download/0.20.5/Clash.for.Windows-0.20.5-x64-linux.tar.gz"><img src="/images/BadgeLinux.png"></a>


        
        

        <h2>لینک تنظیمات:</h2>
روی یکی از لینک های زیر با توجه به نیازتان **راست کلیک** کرده و کپی کنید

        <h3> استفاده هوشمند از فیلترشکن فقط برای سایت های فیلتر و واتساپ و اینستاگرام</h3>

<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/lite-meta.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/lite-meta.yml" class="btn btn-success copylink">کپی لینک</a>

<h3>استفاده هوشمند از فیلترشکن فقط برای سایت های فیلتر</h3>
        
<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/lite.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/lite.yml" class="btn btn-success copylink">کپی لینک</a>

        <h3>
استفاده هوشمند از فیلترشکن فقط برای سایت های خارجی
        </h3>
<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/normal.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/normal.yml" class="btn btn-success copylink">کپی لینک</a>


        <h3>
استفاده از فیلترشکن همیشه (کاهش سرعت سایت های داخلی)
        </h3>
<a href="clash://install-config?url=https://defaultserverhost/defaultusersecret/clash/all.yml" class="btn btn-primary">نصب با یک کلیک</a>
<a href="https://defaultserverhost/defaultusersecret/clash/all.yml" class="btn btn-success copylink">کپی لینک</a>

        <h2>
## کار با کلش ویندوز، مک و لینوکس
        </h2>
چنانچه بر روی دکمه "نصب با یک کلیک" کلیک کرده اید دیگر نیاز به انجام مرحله دوم را ندارید فقط مرحله اول کافی است
ابندا یکی از لینک تنظیمات کلش را کپی کنید و در قسمت 1 تصویر دوم گیف قرار دهید و مراحل را مطابق گیف زیر انجام دهید
{% include figure.html img="clash_windows.gif" alt="How to use clash for windows and macOS" caption="How to use clash for windows and macOS" %}

      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingThree">
      <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
        آیفون - iPhone - iOS
      </button>
    </h2>
    <div id="collapseThree" class="accordion-collapse collapse" aria-labelledby="headingThree" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        ابتدا یکی از نرم افزارهای زیر را دانلود کنید:
        <a href="https://apps.apple.com/us/app/shadowlink-shadowsocks-vpn/id1439686518"><img src="/images/badgeiOS.png"></a>
                
        <h2>
        کار با پروکسی در iOS
        </h2>
ابتدا  بر روی دکمه "نصب با یک کلیک" کلیک کنید و سپس پروکسی را انتخاب و اجرا نمایید. توجه نمایید در iOS نمیتوان رایگان هوشمند کار کرد. 

        
<br/>

<a href="ss://chacha20-ietf-poly1305:defaultusersecret@defaultserverhost:443?plugin=v2ray-plugin%3Bmode%3Dwebsocket%3Bpath%3D%2Fdefaultusersecret%2Fv2ray%2F%3Bhost%3Ddefaultserverhost%3Btls&udp-over-tcp=true#v2ray_defaultserverhost" class="btn btn-primary">نصب کانفیگ 1</a>
<a href="ss://chacha20-ietf-poly1305:defaultusersecret@defaultserverhost:443?plugin=v2ray-plugin%3Bmode%3Dwebsocket%3Bpath%3D%2Fdefaultusersecret%2Fv2ray%2F%3Bhost%3Ddefaultserverhost%3Btls&udp-over-tcp=true#v2ray_defaultserverhost" class="btn btn-success copylink">کپی لینک</a>
        <br/>
        <br/>
        
        {% include figure.html img="ios_shadow.gif" alt="How to use v2 ray for iOS" caption="How to use clash for iOS" %}
        
<a href="ss://chacha20-ietf-poly1305:defaultusersecret@defaultserverhost:443?plugin=obfs-local%3Bobfs%3Dtls%3Bobfs-host%3Dwww.google.com&udp-over-tcp=true#defaultserverhost" class="btn btn-primary">نصب با یک کلیک</a>
<a href="ss://chacha20-ietf-poly1305:defaultusersecret@defaultserverhost:443?plugin=obfs-local%3Bobfs%3Dtls%3Bobfs-host%3Dwww.google.com&udp-over-tcp=true#defaultserverhost" class="btn btn-success copylink">کپی لینک</a>
        
      </div>
    </div>
  </div>
</div>

<style>
.text-break {
    word-wrap: break-word!important;
    word-break: break-word!important;
}
  </style>
<script>
  secret=document.location.pathname.split('/')[1];
  host=document.location.host;
  codes=document.getElementsByTagName('code');
  for (i=0; i<codes.length;i++){
    codes[i].innerHTML=codes[i].innerHTML.replaceAll('defaultusersecret',secret);
    codes[i].innerHTML=codes[i].innerHTML.replaceAll('defaultserverhost',host);
  }

  as=document.getElementsByTagName('a');
  for (i=0; i<as.length;i++){
    as[i].href=as[i].href.replaceAll('defaultusersecret',secret);
    as[i].href=as[i].href.replaceAll('defaultserverhost',host);
    as[i].innerHTML=as[i].innerHTML.replaceAll('defaultusersecret',secret);
    as[i].innerHTML=as[i].innerHTML.replaceAll('defaultserverhost',host);
  }

  copy_links=document.getElementsByClassName('copylink');
  function copy_click(e){
    e.preventDefault(); 
    console.log(this);console.log(e);
    var link=this.href;
    navigator.clipboard.writeText(link).then(function() {
      alert('Link Copied to clipboard '+link);
    }, function(err) {
        window.prompt("Copy to clipboard: Ctrl+C, Enter", link);
    });
  }
  for (i=0; i<copy_links.length;i++){
    copy_links[i].onclick=copy_click;
  }
</script>

  </details>
