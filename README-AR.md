# تحويل التطبيق إلى APK مع قراءة النظام مباشرة

هذه النسخة تقرأ من النظام مباشرة (اسم الجهاز والشركة، إصدار أندرويد، المساحة، البطارية)
عبر إضافة Capacitor Device، وتعمل تلقائياً عند تشغيل التطبيق كـ APK.
ملاحظة: هذه القراءات لا تحتاج أي إذن خطير من المستخدم (لا يظهر طلب إذن)،
وحجم الذاكرة الكلي (RAM) لا يوفّره أندرويد عبر هذه الإضافة، فيبقى خيار الذاكرة يدوياً.

## المتطلبات (مرة واحدة)
1. Node.js (LTS): https://nodejs.org
2. Android Studio: https://developer.android.com/studio (افتحه مرة ليحمّل Android SDK)

## الخطوات (من الطرفية داخل هذا المجلد)

    npm install @capacitor/core @capacitor/cli @capacitor/android @capacitor/device
    npx cap add android
    npx cap sync

## بناء ملف APK
الطريقة 1: `npx cap open android` ثم Build > Build Bundle(s) / APK(s) > Build APK(s)

الطريقة 2:

    cd android
    ./gradlew assembleDebug        (ويندوز: gradlew.bat assembleDebug)

الملف الناتج:  android/app/build/outputs/apk/debug/app-debug.apk

## التثبيت
انقل الملف للجوال وافتحه، وفعّل "السماح بالتثبيت من مصادر غير معروفة" إذا طُلب.

## بعد أي تعديل على www/index.html
    npx cap sync   ثم أعد البناء
