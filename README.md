# 👕 CLOTH POS — نظام كاشير محل الملابس

نظام كاشير متكامل لمحلات الملابس، يعمل كـ Web App ويمكن تثبيته على الموبايل أو الكمبيوتر.

---

## 🚀 رفع على Vercel (خطوات سريعة)

1. ارفع الملفات على GitHub repo جديد
2. روح [vercel.com](https://vercel.com) وسجل دخول بـ GitHub
3. اضغط **Add New Project** واختار الـ repo
4. اضغط **Deploy** — خلاص!

---

## 📁 الملفات

```
index.html      ← كل الكود في ملف واحد
sw.js           ← Service Worker للـ PWA
manifest.json   ← بيانات تطبيق الموبايل
vercel.json     ← إعدادات Vercel
README.md       ← الملف ده
```

---

## ✨ المميزات

| المميزة | الوصف |
|---|---|
| 🛒 كاشير | بيع بالباركود أو البحث |
| 📋 فواتير | سجل كل الفواتير مع فلتر وبحث |
| ↩️ مرتجعات | استرجاع وتبديل منتجات |
| 📦 مخزن | إدارة المنتجات بالمقاسات والألوان |
| 📊 تقارير | اليوم / الأسبوع / الشهر + رسوم بيانية |
| 🖨️ طباعة | فاتورة حرارية 58mm |
| 📱 PWA | تثبيت على الموبايل والكمبيوتر |
| 🌐 Offline | يعمل بدون نت (بيانات محلية) |
| 🔒 PIN | لوجين بباسورد من Firebase |

---

## ⚙️ إعداد Firebase

في ملف `index.html`، ابحث عن `firebaseConfig` وغيّر ببياناتك:

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  ...
};
```

### Firebase Rules (مهم!)
في Firestore Rules، حط:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true; // للاستخدام الداخلي فقط
    }
  }
}
```

---

## 🔑 الباسورد الافتراضي: `1234`

غيّره من **الإعدادات** بعد أول دخول.
