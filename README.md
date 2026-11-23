# مغامرات شحرور في البيت المسكون

لعبة رعب ثلاثية الأبعاد، منظور الشخص الأول، باللغة العربية.
تطوير: حسام.

اللعبة كاملة في ملف واحد `www/index.html`، وكل الصور والأصوات
مضمّنة فيه، فلا تحتاج إنترنت بعد التحميل أو بعد التثبيت.

## كيف تبني APK من GitHub؟

1. ادخل إلى تبويب **Actions** في هذا المستودع.
2. اختر تشغيل **Build APK**، أو ادفع أي تعديل إلى فرع `main`
   فيبدأ البناء تلقائياً.
3. بعد انتهاء البناء، حمّل ملف `shahrour-apk` من قسم
   **Artifacts**، وستجد فيه `app-debug.apk`.
4. انقل الملف إلى هاتف أندرويد وثبّته، وفعّل «التثبيت من مصادر
   غير معروفة» إذا طلبه الهاتف.

اللعبة تعمل بدون نت، وبوضع أفقي على الهواتف.

## البناء محلياً (اختياري)

تحتاج Android Studio مع Android SDK و JDK 17 و Node.js 20:

```bash
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```

ستجد الـ APK في:
`android/app/build/outputs/apk/debug/app-debug.apk`

## ملفات المشروع

- `www/index.html` — اللعبة كاملة (نسخة الويب المصدّرة).
- `capacitor.config.json` — إعدادات Capacitor، معرّف التطبيق
  `com.hessam.shahrour`.
- `package.json` — اعتماديات Capacitor.
- `.github/workflows/build-apk.yml` — بناء الـ APK تلقائياً
  على GitHub Actions.
