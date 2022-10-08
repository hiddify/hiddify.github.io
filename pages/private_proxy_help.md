
# آموزش استفاده از نرم افزار

# چگونه با کلش کار کنیم؟
ابتدا با توجه به سیستم عامل خود یکی از نرم افزارهای زیر را دانلود کنید:
- [![Android: Google Play](/images/google-play-badge.png)](https://play.google.com/store/apps/details?id=com.github.kr328.clash) - [![Android: APK](/images/android-apk-badge.png)](/defaultusersecret/gh/Kr328/ClashForAndroid/releases/download/v2.5.11/cfa-2.5.11-premium-universal-release.apk)
- [![Windows](/images/BadgeWindows.png)](/defaultusersecret/Fndroid/clash_for_windows_pkg/releases/download/0.20.4/Clash.for.Windows.Setup.0.20.4.exe)
- [![macOS](/images/BadgeMacOS.png)](/defaultusersecret/Fndroid/clash_for_windows_pkg/releases/download/0.20.4/Clash.for.Windows-0.20.4.dmg) 
- [![Linux](/images/BadgeLinux.png)](/defaultusersecret/Fndroid/clash_for_windows_pkg/releases/download/0.20.5/Clash.for.Windows-0.20.5-x64-linux.tar.gz)
- [![iOS: Shadowlink](/images/badgeiOS.png)](https://apps.apple.com/us/app/shadowlink-shadowsocks-vpn/id1439686518)




## لینک تنظیمات:
### استفاده هوشمند از فیلترشکن فقط برای سایت های فیلتر

```
https://defaultserverhost/defaultusersecret/clash/lite.yml
```
### استفاده هوشمند از فیلترشکن فقط برای سایت های خارجی

```
https://defaultserverhost/defaultusersecret/clash/normal.yml
```
### استفاده از فیلترشکن همیشه (کاهش سرعت سایت های داخلی)

```
https://defaultserverhost/defaultusersecret/clash/all.yml
```

## کار با کلش ویندوز و مک
  

ابندا یکی از لینک تنظیمات کلش را کپی کنید و در قسمت 1 تصویر دوم گیف قرار دهید و مراحل را مطابق گیف زیر انجام دهید
{% include figure.html img="clash_windows.gif" alt="How to use clash for windows and macOS" caption="How to use clash for windows and macOS" %}


## کار با کلش اندروید
ابندا یکی از لینک تنظیمات کلش را کپی کنید و در بخش 2 مرحله 4 قرار دهید و مراحل را مطابق گیف زیر انجام دهید
{% include figure.html img="clash_android.gif" alt="How to use clash for Android" caption="How to use clash for Android" %}


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
  }

</script>
