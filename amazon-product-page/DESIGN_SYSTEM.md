# 🎨 نظام التصميم - مشروع صفحة منتجات أمازون

## 🎯 نظرة عامة

هذا الملف يوضح نظام التصميم المستخدم في المشروع، بما في ذلك الألوان والخطوط والمسافات والمكونات.

---

## 🌈 نظام الألوان

### 1. الألوان الأساسية

#### ألوان أمازون الأصلية

```css
:root {
  /* الألوان الأساسية */
  --amazon-dark: #131921; /* خلفية الهيدر */
  --amazon-orange: #f0c14b; /* اللون البرتقالي */
  --amazon-blue: #007185; /* اللون الأزرق */
  --amazon-light: #f8f9fa; /* خلفية الصفحة */

  /* ألوان إضافية */
  --amazon-gray: #232f3e; /* خلفية الشريط العلوي */
  --amazon-light-gray: #37475a; /* خلفية العناصر */
  --amazon-border: #3a4553; /* لون الحدود */
}
```

#### استخدام الألوان

```css
/* الهيدر */
.header {
  background-color: var(--amazon-dark);
  color: white;
}

/* الأزرار */
.btn-add-to-cart {
  background-color: var(--amazon-orange);
  color: var(--amazon-dark);
}

/* الروابط */
a {
  color: var(--amazon-blue);
}
```

### 2. ألوان النصوص

#### نظام ألوان النصوص

```css
:root {
  /* ألوان النصوص */
  --text-primary: #0f1111; /* النص الأساسي */
  --text-secondary: #565959; /* النص الثانوي */
  --text-muted: #999; /* النص الباهت */
  --text-white: #ffffff; /* النص الأبيض */
  --text-light: #ddd; /* النص الفاتح */
}
```

#### استخدام ألوان النصوص

```css
/* العناوين */
.product-title {
  color: var(--text-primary);
}

/* النصوص الثانوية */
.price-original {
  color: var(--text-secondary);
}

/* النصوص الباهتة */
.footer-copyright {
  color: var(--text-muted);
}
```

### 3. ألوان الحالات

#### ألوان الحالات المختلفة

```css
:root {
  /* ألوان الحالات */
  --success: #007600; /* النجاح */
  --warning: #ffaa00; /* التحذير */
  --error: #ff4444; /* الخطأ */
  --info: #007185; /* المعلومات */

  /* ألوان التفاعل */
  --hover: #ddb347; /* التمرير */
  --active: #c9a03a; /* النشط */
  --focus: #007185; /* التركيز */
}
```

#### استخدام ألوان الحالات

```css
/* النجاح */
.price-save {
  color: var(--success);
}

/* التحذير */
.warning-message {
  color: var(--warning);
}

/* الخطأ */
.error-message {
  color: var(--error);
}

/* التمرير */
.btn:hover {
  background-color: var(--hover);
}
```

### 4. ألوان الخلفيات

#### نظام ألوان الخلفيات

```css
:root {
  /* خلفيات الصفحة */
  --bg-primary: #f8f9fa; /* خلفية الصفحة */
  --bg-secondary: #ffffff; /* خلفية العناصر */
  --bg-dark: #131921; /* خلفية الهيدر */
  --bg-light: #f8f9fa; /* خلفية فاتحة */

  /* خلفيات العناصر */
  --bg-card: #ffffff; /* خلفية البطاقات */
  --bg-modal: rgba(0, 0, 0, 0.5); /* خلفية النماذج */
  --bg-overlay: rgba(0, 0, 0, 0.1); /* خلفية التراكب */
}
```

#### استخدام ألوان الخلفيات

```css
/* خلفية الصفحة */
body {
  background-color: var(--bg-primary);
}

/* خلفية العناصر */
.product-container {
  background-color: var(--bg-secondary);
}

/* خلفية النماذج */
.modal {
  background-color: var(--bg-modal);
}
```

---

## 🔤 نظام الخطوط

### 1. الخطوط الأساسية

#### الخط الأساسي

```css
:root {
  /* الخط الأساسي */
  --font-family: "Arial", sans-serif;
  --font-family-arabic: "Arial", sans-serif;
  --font-family-english: "Arial", sans-serif;
}
```

#### استخدام الخطوط

```css
/* الخط الأساسي */
body {
  font-family: var(--font-family);
  line-height: 1.6;
}

/* الخط العربي */
[lang="ar"] {
  font-family: var(--font-family-arabic);
}

/* الخط الإنجليزي */
[lang="en"] {
  font-family: var(--font-family-english);
}
```

### 2. أحجام الخطوط

#### نظام أحجام الخطوط

```css
:root {
  /* أحجام الخطوط */
  --font-xs: 12px; /* نصوص صغيرة */
  --font-sm: 14px; /* نصوص متوسطة */
  --font-base: 16px; /* النص الأساسي */
  --font-lg: 18px; /* نصوص كبيرة */
  --font-xl: 24px; /* العناوين */
  --font-2xl: 28px; /* العناوين الكبيرة */
  --font-3xl: 32px; /* العناوين الضخمة */
}
```

#### استخدام أحجام الخطوط

```css
/* النصوص الصغيرة */
.small-text {
  font-size: var(--font-xs);
}

/* النص الأساسي */
body {
  font-size: var(--font-base);
}

/* العناوين */
.product-title {
  font-size: var(--font-xl);
}

/* العناوين الكبيرة */
.main-title {
  font-size: var(--font-2xl);
}
```

### 3. أوزان الخطوط

#### نظام أوزان الخطوط

```css
:root {
  /* أوزان الخطوط */
  --font-light: 300; /* خفيف */
  --font-normal: 400; /* عادي */
  --font-medium: 500; /* متوسط */
  --font-semibold: 600; /* شبه غامق */
  --font-bold: 700; /* غامق */
  --font-extrabold: 800; /* غامق جداً */
}
```

#### استخدام أوزان الخطوط

```css
/* النص العادي */
body {
  font-weight: var(--font-normal);
}

/* النص المتوسط */
.subtitle {
  font-weight: var(--font-medium);
}

/* النص الغامق */
.title {
  font-weight: var(--font-bold);
}
```

---

## 📏 نظام المسافات

### 1. المسافات الأساسية

#### نظام المسافات

```css
:root {
  /* المسافات */
  --space-xs: 5px; /* مسافات صغيرة */
  --space-sm: 10px; /* مسافات متوسطة */
  --space-md: 20px; /* مسافات كبيرة */
  --space-lg: 30px; /* مسافات كبيرة جداً */
  --space-xl: 50px; /* مسافات ضخمة */
  --space-2xl: 80px; /* مسافات ضخمة جداً */
}
```

#### استخدام المسافات

```css
/* المسافات الصغيرة */
.thumbnail {
  margin: var(--space-xs);
}

/* المسافات المتوسطة */
.form-group {
  margin-bottom: var(--space-sm);
}

/* المسافات الكبيرة */
.section {
  padding: var(--space-lg) 0;
}
```

### 2. المسافات الداخلية

#### نظام المسافات الداخلية

```css
:root {
  /* المسافات الداخلية */
  --padding-xs: 5px 10px; /* مسافات صغيرة */
  --padding-sm: 10px 15px; /* مسافات متوسطة */
  --padding-md: 15px 20px; /* مسافات كبيرة */
  --padding-lg: 20px 30px; /* مسافات كبيرة جداً */
  --padding-xl: 30px 40px; /* مسافات ضخمة */
}
```

#### استخدام المسافات الداخلية

```css
/* المسافات الصغيرة */
.btn-small {
  padding: var(--padding-xs);
}

/* المسافات المتوسطة */
.btn-medium {
  padding: var(--padding-sm);
}

/* المسافات الكبيرة */
.btn-large {
  padding: var(--padding-lg);
}
```

### 3. المسافات الخارجية

#### نظام المسافات الخارجية

```css
:root {
  /* المسافات الخارجية */
  --margin-xs: 5px; /* مسافات صغيرة */
  --margin-sm: 10px; /* مسافات متوسطة */
  --margin-md: 20px; /* مسافات كبيرة */
  --margin-lg: 30px; /* مسافات كبيرة جداً */
  --margin-xl: 50px; /* مسافات ضخمة */
}
```

#### استخدام المسافات الخارجية

```css
/* المسافات الصغيرة */
.element {
  margin: var(--margin-xs);
}

/* المسافات الكبيرة */
.section {
  margin: var(--margin-lg) 0;
}
```

---

## 🔲 نظام الحدود

### 1. أنماط الحدود

#### نظام الحدود

```css
:root {
  /* أنماط الحدود */
  --border-none: none; /* بدون حدود */
  --border-solid: 1px solid; /* حدود صلبة */
  --border-dashed: 1px dashed; /* حدود متقطعة */
  --border-dotted: 1px dotted; /* حدود منقطة */

  /* ألوان الحدود */
  --border-light: #ddd; /* حدود فاتحة */
  --border-medium: #999; /* حدود متوسطة */
  --border-dark: #333; /* حدود غامقة */
}
```

#### استخدام الحدود

```css
/* بدون حدود */
.no-border {
  border: var(--border-none);
}

/* حدود فاتحة */
.light-border {
  border: var(--border-solid) var(--border-light);
}

/* حدود غامقة */
.dark-border {
  border: var(--border-solid) var(--border-dark);
}
```

### 2. أنصاف أقطار الحدود

#### نظام أنصاف الأقطار

```css
:root {
  /* أنصاف أقطار الحدود */
  --radius-none: 0; /* بدون انحناء */
  --radius-sm: 4px; /* انحناء صغير */
  --radius-md: 8px; /* انحناء متوسط */
  --radius-lg: 12px; /* انحناء كبير */
  --radius-xl: 16px; /* انحناء ضخم */
  --radius-full: 50%; /* انحناء كامل */
}
```

#### استخدام أنصاف الأقطار

```css
/* بدون انحناء */
.square {
  border-radius: var(--radius-none);
}

/* انحناء صغير */
.btn {
  border-radius: var(--radius-sm);
}

/* انحناء كبير */
.card {
  border-radius: var(--radius-lg);
}

/* انحناء كامل */
.circle {
  border-radius: var(--radius-full);
}
```

---

## 🎭 نظام الظلال

### 1. الظلال الأساسية

#### نظام الظلال

```css
:root {
  /* الظلال */
  --shadow-none: none; /* بدون ظل */
  --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.1); /* ظل صغير */
  --shadow-md: 0 4px 8px rgba(0, 0, 0, 0.1); /* ظل متوسط */
  --shadow-lg: 0 8px 25px rgba(0, 0, 0, 0.15); /* ظل كبير */
  --shadow-xl: 0 20px 60px rgba(0, 0, 0, 0.3); /* ظل ضخم */
}
```

#### استخدام الظلال

```css
/* بدون ظل */
.no-shadow {
  box-shadow: var(--shadow-none);
}

/* ظل صغير */
.card {
  box-shadow: var(--shadow-sm);
}

/* ظل كبير */
.modal {
  box-shadow: var(--shadow-lg);
}
```

### 2. الظلال المخصصة

#### ظلال مخصصة

```css
/* ظل الأزرار */
.btn-shadow {
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

/* ظل العناصر المتفاعلة */
.interactive-shadow {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

/* ظل العناصر المرفوعة */
.elevated-shadow {
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
}
```

---

## ⚡ نظام الانتقالات

### 1. الانتقالات الأساسية

#### نظام الانتقالات

```css
:root {
  /* الانتقالات */
  --transition-none: none; /* بدون انتقال */
  --transition-fast: 0.15s ease; /* انتقال سريع */
  --transition-normal: 0.3s ease; /* انتقال عادي */
  --transition-slow: 0.5s ease; /* انتقال بطيء */
}
```

#### استخدام الانتقالات

```css
/* بدون انتقال */
.no-transition {
  transition: var(--transition-none);
}

/* انتقال سريع */
.fast-transition {
  transition: var(--transition-fast);
}

/* انتقال عادي */
.normal-transition {
  transition: var(--transition-normal);
}
```

### 2. الانتقالات المخصصة

#### انتقالات مخصصة

```css
/* انتقال الأزرار */
.btn-transition {
  transition: all 0.3s ease;
}

/* انتقال العناصر المتفاعلة */
.interactive-transition {
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

/* انتقال النماذج */
.modal-transition {
  transition: opacity 0.3s ease, transform 0.3s ease;
}
```

---

## 🎨 نظام المكونات

### 1. الأزرار

#### أنواع الأزرار

```css
/* الزر الأساسي */
.btn-primary {
  background-color: var(--amazon-orange);
  color: var(--amazon-dark);
  padding: var(--padding-sm);
  border-radius: var(--radius-md);
  border: var(--border-none);
  font-weight: var(--font-bold);
  transition: var(--transition-normal);
}

/* الزر الثانوي */
.btn-secondary {
  background-color: transparent;
  color: var(--amazon-blue);
  border: var(--border-solid) var(--amazon-blue);
  padding: var(--padding-sm);
  border-radius: var(--radius-md);
  font-weight: var(--font-bold);
  transition: var(--transition-normal);
}

/* الزر الكبير */
.btn-large {
  padding: var(--padding-lg);
  font-size: var(--font-lg);
}

/* الزر الصغير */
.btn-small {
  padding: var(--padding-xs);
  font-size: var(--font-sm);
}
```

### 2. الحقول

#### أنواع الحقول

```css
/* الحقل الأساسي */
.input-primary {
  width: 100%;
  padding: var(--padding-sm);
  border: var(--border-solid) var(--border-light);
  border-radius: var(--radius-md);
  font-size: var(--font-base);
  transition: var(--transition-normal);
}

/* الحقل عند التركيز */
.input-primary:focus {
  outline: none;
  border-color: var(--amazon-blue);
  box-shadow: 0 0 0 3px rgba(0, 113, 133, 0.1);
}

/* الحقل مع خطأ */
.input-error {
  border-color: var(--error);
}

/* الحقل مع نجاح */
.input-success {
  border-color: var(--success);
}
```

### 3. البطاقات

#### أنواع البطاقات

```css
/* البطاقة الأساسية */
.card {
  background-color: var(--bg-secondary);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-md);
  padding: var(--padding-lg);
  transition: var(--transition-normal);
}

/* البطاقة المتفاعلة */
.card-interactive {
  cursor: pointer;
}

.card-interactive:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-2px);
}

/* البطاقة المرفوعة */
.card-elevated {
  box-shadow: var(--shadow-xl);
}
```

---

## 📱 نظام التصميم المتجاوب

### 1. Breakpoints

#### نقاط التوقف

```css
:root {
  /* نقاط التوقف */
  --breakpoint-xs: 320px; /* الهواتف الصغيرة جداً */
  --breakpoint-sm: 480px; /* الهواتف */
  --breakpoint-md: 768px; /* الأجهزة اللوحية */
  --breakpoint-lg: 1024px; /* الأجهزة اللوحية الكبيرة */
  --breakpoint-xl: 1200px; /* الشاشات الكبيرة */
  --breakpoint-2xl: 1400px; /* الشاشات الضخمة */
}
```

#### استخدام Breakpoints

```css
/* الهواتف الصغيرة */
@media (max-width: 480px) {
  .container {
    padding: 0 var(--space-sm);
  }
}

/* الأجهزة اللوحية */
@media (max-width: 768px) {
  .product-layout {
    grid-template-columns: 1fr;
    gap: var(--space-lg);
  }
}

/* الشاشات الكبيرة */
@media (min-width: 1200px) {
  .container {
    max-width: var(--breakpoint-xl);
  }
}
```

### 2. التخطيط المتجاوب

#### نظام التخطيط

```css
/* التخطيط المرن */
.flex-layout {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-md);
}

/* التخطيط الشبكي */
.grid-layout {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--space-lg);
}

/* التخطيط المتجاوب */
.responsive-layout {
  display: grid;
  grid-template-columns: 1fr;
}

@media (min-width: 768px) {
  .responsive-layout {
    grid-template-columns: 1fr 1fr;
  }
}

@media (min-width: 1200px) {
  .responsive-layout {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
```

---

## 🎯 أفضل الممارسات

### 1. استخدام المتغيرات

#### المتغيرات الموصى بها

```css
/* استخدم المتغيرات بدلاً من القيم المباشرة */
.btn {
  background-color: var(--amazon-orange); /* ✅ جيد */
  /* background-color: #f0c14b; */ /* ❌ سيء */
}

/* استخدم المتغيرات للمسافات */
.section {
  padding: var(--space-lg) 0; /* ✅ جيد */
  /* padding: 30px 0; */ /* ❌ سيء */
}
```

### 2. التسمية

#### تسمية المتغيرات

```css
/* استخدم أسماء واضحة */
:root {
  --color-primary: #f0c14b; /* ✅ جيد */
  --color-main: #f0c14b; /* ❌ سيء */

  --spacing-large: 30px; /* ✅ جيد */
  --spacing-big: 30px; /* ❌ سيء */
}
```

### 3. التنظيم

#### تنظيم CSS

```css
/* رتب القواعد منطقياً */
/* 1. المتغيرات */
:root {
  ...;
}

/* 2. الإعدادات العامة */
* {
  ...;
}
body {
  ...;
}

/* 3. المكونات */
.header {
  ...;
}
.main {
  ...;
}
.footer {
  ...;
}

/* 4. التصميم المتجاوب */
@media (max-width: 768px) {
  ...;
}
```

---

## 🚀 الخلاصة

نظام التصميم هذا يوفر أساساً قوياً ومتسقاً لجميع عناصر المشروع. استخدام المتغيرات يجعل التخصيص والتطوير أسهل وأسرع.

**استخدم هذا النظام لضمان الاتساق والجودة!** 🎨

---

**تم إنشاء هذا الملف بواسطة:** Tarek al sabbagh
**التاريخ:** 2025
**الإصدار:** 1.0.0
