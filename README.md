# 🎭 مافيا — لعبة أونلاين

## خطوات الإعداد (مجانية 100%)

### 1️⃣ إنشاء مشروع Firebase (مجاني)

1. اذهب إلى: **https://console.firebase.google.com**
2. اضغط **"Add project"** → أدخل اسماً → Next → Next → Create project
3. من القائمة الجانبية: **Build → Realtime Database**
4. اضغط **"Create Database"** → اختر أي موقع → ابدأ بـ **"Test mode"** (مؤقتاً)
5. انسخ رابط قاعدة البيانات مثل: `https://your-project-default-rtdb.firebaseio.com`

### 2️⃣ الحصول على إعدادات Firebase

1. من الصفحة الرئيسية للمشروع اضغط على أيقونة **</>** (Web App)
2. أدخل اسم التطبيق واضغط **Register app**
3. انسخ الـ `firebaseConfig` كاملاً

### 3️⃣ تعديل ملف index.html

افتح `index.html` وابحث عن هذا المقطع (السطر ~425):

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyDemo_Replace_With_Yours",
  authDomain: "mafia-game-demo.firebaseapp.com",
  databaseURL: "https://mafia-game-demo-default-rtdb.firebaseio.com",
  ...
};
```

**استبدله** بإعداداتك الخاصة من Firebase.

### 4️⃣ ضبط قواعد قاعدة البيانات

في Firebase Console → Realtime Database → **Rules**، ضع:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

> ⚠️ هذا للتجربة فقط. للإنتاج استخدم قواعد أكثر أماناً.

### 5️⃣ الرفع على GitHub Pages

```bash
git init
git add .
git commit -m "Mafia Game Online"
git branch -M main
git remote add origin https://github.com/USERNAME/mafia-game.git
git push -u origin main
```

ثم في GitHub → Settings → Pages → Source: **main branch** → Save

رابط اللعبة: `https://USERNAME.github.io/mafia-game`

### 5️⃣ الرفع على Hostinger

1. اضغط على ملف `MafiaGame-Online.zip`
2. في لوحة Hostinger → File Manager → `public_html`
3. ارفع الـ ZIP واستخرجه هناك

---

## 🎮 كيف تلعب أونلاين

1. **الهوست** يفتح اللعبة → "لعب أونلاين" → "إنشاء غرفة"
2. يشارك **كود الغرفة** (4 أحرف) مع الأصدقاء
3. كل لاعب يدخل باسمه + كود الغرفة
4. الهوست يضبط الإعدادات والأدوار → "ابدأ اللعبة"
5. كل لاعب يرى دوره على جهازه الخاص
6. في الليل: كل لاعب ينفذ دوره بشكل مستقل
7. في النهار: النقاش + التصويت — الهوست يتحكم بالإعدام

## 📱 المتطلبات
- متصفح حديث (Chrome / Safari / Firefox)
- اتصال بالإنترنت للأونلاين
- Firebase مجاني (Spark Plan) يكفي حتى 100 لاعب متزامن
