# 🛒 مشروع صفحة منتجات أمازون - دليل شامل

## 📋 نظرة عامة على المشروع

هذا المشروع عبارة عن صفحة منتجات أمازون كاملة ومتطورة تم تطويرها باستخدام **HTML5** و **CSS3** فقط، بدون استخدام أي JavaScript. المشروع يدعم اللغتين العربية والإنجليزية مع تصميم متجاوب يعمل على جميع الأجهزة.

---

## 🎯 أهداف المشروع

- إنشاء صفحة منتجات أمازون احترافية
- دعم اللغتين العربية والإنجليزية
- تصميم متجاوب (Responsive Design)
- عدم استخدام JavaScript (CSS فقط)
- تطبيق أفضل الممارسات في التطوير

---

## 📁 هيكل المشروع

```
amazon-product-page/
├── index.html          # الصفحة الرئيسية (العربية)
├── index-en.html       # الصفحة الإنجليزية
├── style.css           # ملف التنسيقات الرئيسي
├── .vscode/
│   └── settings.json   # إعدادات Cursor للحفظ التلقائي
└── README.md           # هذا الملف
```

---

## 🛠️ التقنيات المستخدمة

### 1. HTML5

- **Semantic HTML**: استخدام العناصر الدلالية مثل `<header>`, `<main>`, `<section>`, `<footer>`
- **Accessibility**: دعم إمكانية الوصول مع `alt` attributes و `aria-labels`
- **Form Elements**: نماذج تسجيل الدخول وإنشاء الحساب
- **Meta Tags**: إعدادات SEO والتصميم المتجاوب

### 2. CSS3

- **Flexbox**: لتخطيط العناصر المرنة
- **CSS Grid**: لتخطيط الشبكة المتقدمة
- **CSS Variables**: للمتغيرات القابلة لإعادة الاستخدام
- **Media Queries**: للتصميم المتجاوب
- **CSS Animations**: للانتقالات والتأثيرات
- **CSS Pseudo-classes**: للتفاعل بدون JavaScript

### 3. CSS-Only Interactions

- **Checkbox Hack**: لإظهار/إخفاء النماذج
- **Focus States**: للتفاعل مع لوحة المفاتيح
- **Hover Effects**: للتأثيرات البصرية
- **Transition Effects**: للانتقالات السلسة

---

## 🎨 التصميم والواجهة

### الألوان المستخدمة

```css
/* ألوان أمازون الأصلية */
--amazon-dark: #131921; /* خلفية الهيدر */
--amazon-orange: #f0c14b; /* اللون البرتقالي */
--amazon-blue: #007185; /* اللون الأزرق */
--amazon-light: #f8f9fa; /* خلفية الصفحة */
```

### الخطوط

- **Arial**: الخط الأساسي للنصوص
- **Font Weights**: 400 (عادي), 600 (متوسط), 700 (غامق)

### التخطيط

- **Container**: عرض أقصى 1200px مع padding جانبي
- **Grid System**: نظام شبكة مرن للعناصر
- **Responsive Breakpoints**: 768px و 480px

---

## 📱 المكونات الرئيسية

### 1. الهيدر (Header)

```html
<header class="header">
  <!-- الشريط العلوي -->
  <div class="top-bar">
    <!-- رسالة التوصيل المجاني -->
    <!-- أزرار تسجيل الدخول -->
  </div>

  <!-- الهيدر الرئيسي -->
  <div class="main-header">
    <!-- الشعار -->
    <!-- شريط البحث -->
    <!-- قائمة المستخدم -->
  </div>

  <!-- شريط التنقل -->
  <nav class="navigation">
    <!-- قائمة الفئات -->
  </nav>
</header>
```

**المميزات:**

- شعار أمازون قابل للنقر
- شريط بحث مع قائمة الفئات
- قائمة المستخدم مع عربة التسوق
- شريط تنقل مع الفئات الرئيسية

### 2. مسار التنقل (Breadcrumb)

```html
<nav class="breadcrumb-nav">
  <a href="#">الرئيسية</a> › <a href="#">سوريا</a> ›
  <a href="#">الإلكترونيات</a> ›
  <span>iPhone 15 Pro Max</span>
</nav>
```

**الوظيفة:**

- يوضح موقع المستخدم في الموقع
- روابط قابلة للنقر للعودة للصفحات السابقة

### 3. معرض الصور (Product Gallery)

```html
<section class="product-gallery">
  <div class="gallery-main">
    <!-- الصورة الرئيسية -->
    <div class="product-image-placeholder">
      <!-- محاكاة هاتف iPhone -->
    </div>
  </div>

  <div class="gallery-thumbnails">
    <!-- الصور المصغرة -->
  </div>
</section>
```

**المميزات:**

- صورة رئيسية كبيرة للمنتج
- 5 صور مصغرة بألوان مختلفة
- تأثيرات تفاعلية عند التركيز
- محاكاة ثلاثية الأبعاد للهاتف

### 4. معلومات المنتج (Product Info)

```html
<section class="product-info">
  <div class="product-header">
    <!-- عنوان المنتج -->
    <!-- التقييم والنجوم -->
  </div>

  <div class="product-price">
    <!-- السعر الحالي -->
    <!-- السعر الأصلي -->
    <!-- مبلغ التوفير -->
  </div>

  <div class="product-features">
    <!-- قائمة المميزات -->
  </div>

  <div class="product-options">
    <!-- خيارات الألوان -->
    <!-- خيارات السعة -->
  </div>

  <div class="product-actions">
    <!-- أزرار الشراء -->
  </div>

  <div class="product-delivery">
    <!-- خيارات التوصيل -->
  </div>
</section>
```

**المحتوى:**

- عنوان المنتج مع التقييم
- عرض السعر مع الخصم
- قائمة المميزات الرئيسية
- خيارات الألوان والسعة
- أزرار الشراء والإجراءات
- معلومات التوصيل والدفع

### 5. النماذج (Forms)

```html
<!-- نموذج تسجيل الدخول -->
<input type="checkbox" id="loginTrigger" class="modal-trigger" />
<div id="loginModal" class="modal">
  <form class="auth-form">
    <!-- حقول تسجيل الدخول -->
  </form>
</div>

<!-- نموذج إنشاء الحساب -->
<input type="checkbox" id="registerTrigger" class="modal-trigger" />
<div id="registerModal" class="modal">
  <form class="auth-form">
    <!-- حقول إنشاء الحساب -->
  </form>
</div>
```

**المميزات:**

- نماذج منبثقة بدون JavaScript
- حقول شاملة للبيانات
- التحقق من صحة البيانات
- تصميم جميل ومتجاوب

### 6. الفوتر (Footer)

```html
<footer class="footer">
  <!-- زر العودة للأعلى -->
  <div class="back-to-top">
    <button class="back-to-top-btn">العودة للأعلى</button>
  </div>

  <!-- المحتوى الرئيسي -->
  <div class="footer-content">
    <!-- أقسام الفوتر -->
  </div>

  <!-- شريط اللغات -->
  <div class="footer-languages">
    <!-- روابط اللغات -->
  </div>

  <!-- الفوتر السفلي -->
  <div class="footer-bottom">
    <!-- حقوق النشر -->
  </div>
</footer>
```

**المحتوى:**

- زر العودة لأعلى الصفحة
- أقسام متنوعة للمعلومات
- شريط اختيار اللغات
- حقوق النشر والروابط

---

## 🔧 التقنيات المتقدمة المستخدمة

### 1. CSS Grid Layout

```css
.product-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  align-items: start;
}

.footer-sections {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
}
```

**الاستخدام:**

- تخطيط المنتج الرئيسي
- تخطيط أقسام الفوتر
- تخطيط مرن يتكيف مع المحتوى

### 2. Flexbox Layout

```css
.header-content {
  display: flex;
  align-items: center;
  gap: 20px;
}

.product-actions {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}
```

**الاستخدام:**

- تخطيط الهيدر
- تخطيط أزرار الإجراءات
- تخطيط العناصر المرنة

### 3. CSS Animations

```css
@keyframes modalSlideIn {
  from {
    opacity: 0;
    transform: translateY(-50px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.modal-content {
  animation: modalSlideIn 0.3s ease-out;
}
```

**الاستخدام:**

- انتقالات النماذج
- تأثيرات التمرير
- انتقالات العناصر

### 4. CSS Transitions

```css
.btn-add-to-cart {
  transition: all 0.3s;
}

.btn-add-to-cart:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}
```

**الاستخدام:**

- انتقالات الأزرار
- تأثيرات التمرير
- انتقالات العناصر

### 5. CSS Pseudo-classes

```css
/* تأثيرات التركيز */
.thumbnail:focus {
  border-color: #f0c14b;
  box-shadow: 0 0 0 2px #f0c14b;
}

/* تأثيرات التمرير */
.btn-add-to-cart:hover {
  background-color: #ddb347;
}

/* تأثيرات النشاط */
.btn-add-to-cart:active {
  transform: scale(0.98);
}
```

**الاستخدام:**

- التفاعل بدون JavaScript
- تحسين إمكانية الوصول
- تجربة مستخدم أفضل

---

## 📱 التصميم المتجاوب (Responsive Design)

### Breakpoints

```css
/* الهواتف الصغيرة */
@media (max-width: 480px) {
  .container {
    padding: 0 10px;
  }

  .product-title {
    font-size: 18px;
  }
}

/* الأجهزة اللوحية */
@media (max-width: 768px) {
  .product-layout {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .header-content {
    flex-direction: column;
    gap: 15px;
  }
}
```

### استراتيجية التصميم المتجاوب

1. **Mobile First**: البدء بالهواتف ثم التوسع
2. **Flexible Grid**: شبكة مرنة تتكيف مع الشاشة
3. **Responsive Images**: صور تتكيف مع الحجم
4. **Touch-Friendly**: عناصر مناسبة للمس

---

## 🎨 نظام الألوان والتصميم

### لوحة الألوان

```css
/* الألوان الأساسية */
--primary-dark: #131921; /* خلفية الهيدر */
--primary-orange: #f0c14b; /* اللون البرتقالي */
--primary-blue: #007185; /* اللون الأزرق */
--primary-light: #f8f9fa; /* خلفية الصفحة */

/* ألوان النصوص */
--text-primary: #0f1111; /* النص الأساسي */
--text-secondary: #565959; /* النص الثانوي */
--text-muted: #999; /* النص الباهت */

/* ألوان الحالات */
--success: #007600; /* النجاح */
--warning: #ffaa00; /* التحذير */
--error: #ff4444; /* الخطأ */
```

### نظام الخطوط

```css
/* الخطوط الأساسية */
body {
  font-family: "Arial", sans-serif;
  line-height: 1.6;
}

/* أحجام الخطوط */
--font-xs: 12px; /* نصوص صغيرة */
--font-sm: 14px; /* نصوص متوسطة */
--font-base: 16px; /* النص الأساسي */
--font-lg: 18px; /* نصوص كبيرة */
--font-xl: 24px; /* العناوين */
--font-2xl: 28px; /* العناوين الكبيرة */
```

### نظام المسافات

```css
/* المسافات */
--space-xs: 5px; /* مسافات صغيرة */
--space-sm: 10px; /* مسافات متوسطة */
--space-md: 20px; /* مسافات كبيرة */
--space-lg: 30px; /* مسافات كبيرة جداً */
--space-xl: 50px; /* مسافات ضخمة */
```

---

## 🔍 إمكانية الوصول (Accessibility)

### 1. HTML Semantic

```html
<!-- استخدام العناصر الدلالية -->
<header>
  <!-- رأس الصفحة -->
  <main>
    <!-- المحتوى الرئيسي -->
    <section>
      <!-- أقسام المحتوى -->
      <nav>
        <!-- التنقل -->
        <footer><!-- تذييل الصفحة --></footer>
      </nav>
    </section>
  </main>
</header>
```

### 2. ARIA Labels

```html
<!-- تسميات للعناصر -->
<button aria-label="إغلاق النموذج" class="close">&times;</button>
<input aria-describedby="password-help" type="password" />
```

### 3. Keyboard Navigation

```css
/* دعم التنقل بلوحة المفاتيح */
button:focus,
input:focus,
a:focus {
  outline: 2px solid #007185;
  outline-offset: 2px;
}
```

### 4. Color Contrast

- **نسبة التباين**: 4.5:1 على الأقل
- **الألوان**: متباينة وواضحة
- **النصوص**: قابلة للقراءة

---

## 🌐 دعم اللغات

### 1. الصفحة العربية (index.html)

```html
<html lang="ar" dir="rtl">
  <head>
    <meta charset="UTF-8" />
    <title>صفحة منتج أمازون - سوريا</title>
  </head>
</html>
```

**المميزات:**

- اتجاه النص من اليمين لليسار (RTL)
- نصوص باللغة العربية
- أسعار بالليرة السورية
- مدن سورية في النماذج

### 2. الصفحة الإنجليزية (index-en.html)

```html
<html lang="en" dir="ltr">
  <head>
    <meta charset="UTF-8" />
    <title>Amazon Product Page - Syria</title>
  </head>
</html>
```

**المميزات:**

- اتجاه النص من اليسار لليمين (LTR)
- نصوص باللغة الإنجليزية
- نفس المحتوى مترجم
- نفس التصميم والوظائف

### 3. التبديل بين اللغات

```html
<!-- في الصفحة العربية -->
<a href="index-en.html" class="language-link">
  <span class="flag">🇺🇸</span>
  <span>English</span>
</a>

<!-- في الصفحة الإنجليزية -->
<a href="index.html" class="language-link">
  <span class="flag">🇸🇾</span>
  <span>العربية</span>
</a>
```

---

## 🚀 الأداء والتحسين

### 1. تحسين CSS

```css
/* استخدام CSS Variables */
:root {
  --primary-color: #f0c14b;
  --secondary-color: #131921;
}

/* استخدام Shorthand Properties */
.btn {
  margin: 10px 15px;
  padding: 12px 24px;
  border: none;
  border-radius: 8px;
}
```

### 2. تحسين الصور

```css
/* صور متجاوبة */
.product-image {
  max-width: 100%;
  height: auto;
  object-fit: cover;
}
```

### 3. تحسين الخطوط

```css
/* تحميل الخطوط المحلية */
body {
  font-family: "Arial", sans-serif;
  font-display: swap;
}
```

---

## 🧪 الاختبار والتطوير

### 1. اختبار المتصفحات

- **Chrome**: ✅ متوافق
- **Firefox**: ✅ متوافق
- **Safari**: ✅ متوافق
- **Edge**: ✅ متوافق

### 2. اختبار الأجهزة

- **Desktop**: ✅ متوافق
- **Tablet**: ✅ متوافق
- **Mobile**: ✅ متوافق

### 3. اختبار إمكانية الوصول

- **Screen Readers**: ✅ متوافق
- **Keyboard Navigation**: ✅ متوافق
- **Color Blindness**: ✅ متوافق

---

## 📚 المراجع والمصادر

### 1. معايير الويب

- [W3C HTML5 Specification](https://www.w3.org/TR/html5/)
- [W3C CSS3 Specification](https://www.w3.org/TR/css3-roadmap/)
- [Web Accessibility Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)

### 2. أدوات التطوير

- **Cursor**: محرر النصوص
- **Git**: إدارة الإصدارات
- **Browser DevTools**: أدوات المطور

### 3. مصادر التصميم

- [Amazon Design System](https://design.amazon.com/)
- [Material Design](https://material.io/design)
- [Bootstrap](https://getbootstrap.com/)

---

## 🔧 إعدادات التطوير

### 1. إعدادات Cursor

```json
{
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 1000,
  "files.autoSaveWhenNoErrors": true,
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll": true
  }
}
```

### 2. إعدادات Git

```bash
# تهيئة المشروع
git init
git add .
git commit -m "Initial commit: Amazon product page"

# إضافة الملفات
git add index.html index-en.html style.css README.md
git commit -m "Add main project files"
```

---

## 🎯 الميزات المستقبلية

### 1. تحسينات مقترحة

- [ ] إضافة المزيد من اللغات
- [ ] تحسين الأداء
- [ ] إضافة المزيد من المنتجات
- [ ] تحسين SEO

### 2. ميزات إضافية

- [ ] نظام البحث
- [ ] تصفية المنتجات
- [ ] مقارنة المنتجات
- [ ] نظام التقييمات

---

## 📞 الدعم والمساعدة

### 1. المشاكل الشائعة

- **النماذج لا تظهر**: تأكد من أن CSS محمل بشكل صحيح
- **التصميم لا يعمل**: تحقق من دعم المتصفح للـ CSS Grid
- **الخطوط لا تظهر**: تأكد من وجود الخطوط في النظام

### 2. الحصول على المساعدة

- راجع هذا الملف أولاً
- تحقق من الكود في المتصفح
- استخدم أدوات المطور للتحقق من الأخطاء

---

## 📄 الترخيص

هذا المشروع مخصص للأغراض التعليمية والتطوير. يمكن استخدامه كمرجع لتعلم HTML و CSS.

---

## 🏆 الخلاصة

هذا المشروع يوضح كيفية إنشاء صفحة منتجات احترافية باستخدام HTML و CSS فقط، مع التركيز على:

- **التصميم المتجاوب**
- **إمكانية الوصول**
- **دعم اللغات المتعددة**
- **التفاعل بدون JavaScript**
- **أفضل الممارسات في التطوير**

المشروع جاهز للاستخدام ويمكن تطويره وإضافة المزيد من الميزات حسب الحاجة.

---

**تم إنشاء هذا المشروع بواسطة:** Tarek al sabbagh
**التاريخ:** 2025
**الإصدار:** 1.0.0
