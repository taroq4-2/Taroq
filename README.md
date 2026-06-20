# 🛡️ Taroq OS — حاجب الإعلانات الشامل

<div align="center">

**مفتوح المصدر | بدون root | يحجب كل الإعلانات**

[![Build APK](https://github.com/Taro0q/TaroqOS/actions/workflows/build.yml/badge.svg)](https://github.com/Taro0q/TaroqOS/actions/workflows/build.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-teal.svg)](LICENSE)
[![Android](https://img.shields.io/badge/Android-8.0%2B-green.svg)](https://android.com)

🌐 [os73.com](https://os73.com) &nbsp;|&nbsp; 📷 [@Taro0q](https://instagram.com/Taro0q)

</div>

---

## كيفية الحصول على APK

### الطريقة الأولى: GitHub Actions (تلقائية — الأسرع)
1. ارفع هذا المشروع على GitHub
2. اذهب لـ `Actions` ← `Build Taroq OS APK`
3. اضغط `Run workflow`
4. بعد انتهاء البناء، حمّل الـ APK من `Artifacts`

### الطريقة الثانية: Android Studio (الأسهل محلياً)
1. افتح `Android Studio` ← `File → Open` ← اختر مجلد `TaroqOS`
2. انتظر مزامنة Gradle
3. `Build → Build Bundle(s) / APK(s) → Build APK(s)`
4. APK في: `app/build/outputs/apk/debug/`

### الطريقة الثالثة: Command Line
```bash
cd TaroqOS
./gradlew assembleDebug
# APK: app/build/outputs/apk/debug/app-debug.apk
```

---

## آلية العمل — ثلاث طبقات حماية

```
┌─────────────────────────────────────────────────────────────┐
│                    Taroq OS Shield                          │
│                                                             │
│  1. فلتر DNS  — يحجب 500+ نطاق إعلاني بالاسم              │
│  2. فلتر SNI  — يقرأ وجهة HTTPS قبل التشفير ★ ابتكار       │
│  3. فلتر JSON — يحذف الإعلانات من ردود API للتطبيقات       │
│                                                             │
│  جميع العمليات محلية — لا بيانات تغادر جهازك              │
└─────────────────────────────────────────────────────────────┘
```

### ★ الابتكار: فلتر SNI
يقرأ حقل **Server Name Indication** من حزمة TLS ClientHello **قبل التشفير**.
هذا يكشف وجهة كل اتصال HTTPS حتى عند استخدام:
- عناوين IP مباشرة (تتجاوز DNS)
- DNS-over-HTTPS
- CDN مشترك مع محتوى حقيقي

### نسبة الفعالية المتوقعة
| التطبيق    | الفعالية |
|------------|----------|
| Facebook   | ~85-92%  |
| Instagram  | ~80-90%  |
| Snapchat   | ~75-85%  |
| TikTok     | ~85-95%  |
| Twitter/X  | ~70-80%  |
| YouTube    | ~60-75%  |
| تطبيقات أخرى| ~70-85% |

---

## الأذونات المطلوبة
| الإذن | السبب |
|-------|-------|
| `INTERNET` | الاتصال بالشبكة |
| `FOREGROUND_SERVICE` | التشغيل المستمر في الخلفية |
| `VPN` | إنشاء نفق VPN محلي |
| `RECEIVE_BOOT_COMPLETED` | البدء التلقائي مع الجهاز |
| `POST_NOTIFICATIONS` | الإشعار الدائم |

---

## الخصوصية والأمان
- ✅ لا يجمع أي بيانات شخصية
- ✅ لا يرسل أي معلومات للخارج
- ✅ كل الفلترة تتم محلياً على الجهاز
- ✅ الكود المصدري مفتوح للمراجعة الكاملة
- ✅ لا يتطلب صلاحيات root

---

## المتطلبات
- Android 8.0 (API 26) أو أعلى
- لا يحتاج root

---

## المطور
- 🌐 الموقع: [os73.com](https://os73.com)
- 📷 Instagram: [@Taro0q](https://instagram.com/Taro0q)
- 🐙 GitHub: [Taro0q/TaroqOS](https://github.com/Taro0q/TaroqOS)

---

## الرخصة
MIT License — حر الاستخدام والتعديل والتوزيع
