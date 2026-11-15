# تلاش نو | Talasheno

تلاش نو یک برنامه فارسی و راست‌چین با رویکرد موبایل‌محور است.

## اجرای نسخه وب
فایل اصلی رابط کاربری در ریشه مخزن با نام `index.html` قرار دارد. برای انتشار وب، GitHub Pages از همین فایل استفاده می‌کند.

## ساخت APK اندروید
پروژه از Capacitor 7 برای بسته‌بندی نسخه وب در برنامه اندروید استفاده می‌کند.

پیش‌نیازهای ساخت محلی:
- Node.js 22
- Java JDK 21
- Android SDK و ابزارهای Android Build

دستورها:
```bash
npm install
npm run build:web
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

فایل خروجی نسخه آزمایشی:
`android/app/build/outputs/apk/debug/app-debug.apk`

## ساخت خودکار در GitHub
از مسیر Actions، گردش‌کار **Build Talasheno Android APK** را با گزینه Run workflow اجرا کنید. همچنین تغییرات مرتبط در شاخه `main` به‌صورت خودکار ساخت را فعال می‌کند. APK موفق به‌عنوان Artifact با نام `Talasheno-debug-APK` قابل دریافت است.

## نکته امنیتی
کلیدها، رمزها و فایل‌های امضای نسخه انتشار را در مخزن عمومی قرار ندهید. نسخه فعلی گردش‌کار، APK آزمایشی (debug) می‌سازد و برای انتشار عمومی فروشگاهی باید امضای امن release جداگانه تنظیم شود.
