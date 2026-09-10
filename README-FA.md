# همراه چله — نسخه مستقل اندروید

این پروژه نسخه وب موجود را به‌عنوان فایل‌های محلی داخل APK اجرا می‌کند. اجرای خود برنامه به GitHub Pages وابسته نیست.

## ساخت روی Android/Termux

1. Node.js و Java 17 را نصب کنید.
2. داخل این پوشه اجرا کنید:

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

در ویندوز به‌جای `./gradlew` از `gradlew.bat` استفاده کنید.

APK خروجی:
`android/app/build/outputs/apk/debug/app-debug.apk`

## نکته درباره Supabase

کد فعلی برنامه از Supabase برای احراز هویت/همگام‌سازی استفاده می‌کند و کتابخانه Supabase را از CDN بارگذاری می‌کند. بنابراین خود رابط برنامه محلی است، اما ورود/ثبت‌نام و همگام‌سازی Supabase اینترنت می‌خواهد. اگر CDN در دسترس نباشد، بخش Supabase کار نمی‌کند.

برای آفلاینِ کامل باید لایه حساب/همگام‌سازی نیز جداگانه به ذخیره‌سازی محلی منتقل شود یا کتابخانه Supabase به‌صورت محلی vendor شود.
