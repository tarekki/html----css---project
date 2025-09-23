# 📖 دليل الكود التفصيلي - مشروع صفحة منتجات أمازون

## 🎯 مقدمة

هذا الدليل يشرح كل سطر من الكود المستخدم في المشروع، مع شرح مفصل لكل تقنية وكل CSS class وكل HTML element.

---

## 📁 ملفات المشروع

### 1. index.html - الصفحة الرئيسية العربية

#### الهيكل الأساسي

```html
<!DOCTYPE html>
<html lang="ar" dir="rtl"></html>
```

**الشرح:**

- `<!DOCTYPE html>`: يخبر المتصفح أن هذا ملف HTML5
- `lang="ar"`: يحدد اللغة العربية للمحتوى
- `dir="rtl"`: يحدد اتجاه النص من اليمين لليسار

#### Meta Tags

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="description" content="صفحة منتج أمازون - تسوق آمن وسريع في سوريا" />
```

**الشرح:**

- `charset="UTF-8"`: يدعم جميع الأحرف العربية والإنجليزية
- `viewport`: يجعل الموقع متجاوب مع الأجهزة المحمولة
- `description`: وصف الصفحة لمحركات البحث

---

## 🎨 ملف style.css - التنسيقات

### 1. إعدادات عامة

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

**الشرح:**

- `*`: يطبق على جميع العناصر
- `margin: 0; padding: 0;`: يزيل المسافات الافتراضية
- `box-sizing: border-box;`: يجعل العرض يشمل الـ padding والـ border

### 2. إعدادات الجسم

```css
body {
  font-family: "Arial", sans-serif;
  line-height: 1.6;
  color: #333;
  background-color: #f8f9fa;
}
```

**الشرح:**

- `font-family`: يحدد الخط الأساسي
- `line-height: 1.6`: يحدد المسافة بين الأسطر
- `color: #333`: لون النص الأساسي
- `background-color: #f8f9fa`: لون خلفية الصفحة

### 3. Container

```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}
```

**الشرح:**

- `max-width: 1200px`: أقصى عرض للمحتوى
- `margin: 0 auto`: يوسط المحتوى
- `padding: 0 20px`: مسافة جانبية

---

## 🏗️ الهيدر (Header)

### 1. الهيكل الأساسي

```html
<header class="header">
  <div class="top-bar">
    <div class="container">
      <div class="top-bar-content">
        <!-- المحتوى -->
      </div>
    </div>
  </div>
</header>
```

### 2. CSS للهيدر

```css
.header {
  background-color: #131921;
  color: white;
  position: sticky;
  top: 0;
  z-index: 1000;
}
```

**الشرح:**

- `background-color: #131921`: لون خلفية الهيدر (أسود أمازون)
- `color: white`: لون النص
- `position: sticky`: يلتصق الهيدر عند التمرير
- `top: 0`: يلتصق من أعلى الصفحة
- `z-index: 1000`: يظهر فوق العناصر الأخرى

### 3. الشريط العلوي

```css
.top-bar {
  background-color: #232f3e;
  padding: 8px 0;
  font-size: 14px;
}
```

**الشرح:**

- `background-color: #232f3e`: لون مختلف للشريط العلوي
- `padding: 8px 0`: مسافة علوية وسفلية
- `font-size: 14px`: حجم خط أصغر

### 4. تخطيط الشريط العلوي

```css
.top-bar-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

**الشرح:**

- `display: flex`: يجعل العناصر في صف واحد
- `justify-content: space-between`: يوزع العناصر مع مسافة بينها
- `align-items: center`: يوسط العناصر عمودياً

---

## 🔍 شريط البحث

### 1. HTML

```html
<div class="search-bar">
  <form class="search-form">
    <select class="search-category">
      <option>جميع الفئات</option>
      <option>الإلكترونيات</option>
    </select>
    <input type="text" placeholder="ابحث عن منتج..." class="search-input" />
    <button type="submit" class="search-btn">🔍</button>
  </form>
</div>
```

### 2. CSS

```css
.search-bar {
  flex: 1;
  max-width: 600px;
}

.search-form {
  display: flex;
  height: 40px;
}
```

**الشرح:**

- `flex: 1`: يأخذ المساحة المتبقية
- `max-width: 600px`: أقصى عرض للشريط
- `display: flex`: يجعل العناصر في صف واحد
- `height: 40px`: ارتفاع ثابت

### 3. حقل البحث

```css
.search-input {
  flex: 1;
  border: none;
  padding: 0 15px;
  font-size: 16px;
  outline: none;
}
```

**الشرح:**

- `flex: 1`: يأخذ المساحة المتبقية
- `border: none`: يزيل الحدود
- `padding: 0 15px`: مسافة داخلية
- `outline: none`: يزيل الحدود عند التركيز

---

## 🛒 معرض الصور

### 1. الهيكل

```html
<section class="product-gallery">
  <div class="gallery-main">
    <div class="main-image">
      <div class="product-image-placeholder">
        <div class="image-content">
          <div class="phone-mockup">
            <!-- محاكاة الهاتف -->
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="gallery-thumbnails">
    <!-- الصور المصغرة -->
  </div>
</section>
```

### 2. الصورة الرئيسية

```css
.product-image-placeholder {
  width: 100%;
  height: 400px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

**الشرح:**

- `width: 100%`: يأخذ العرض الكامل
- `height: 400px`: ارتفاع ثابت
- `background: linear-gradient`: تدرج لوني جميل
- `border-radius: 12px`: زوايا مدورة
- `display: flex`: لتوسيط المحتوى

### 3. محاكاة الهاتف

```css
.phone-mockup {
  width: 200px;
  height: 350px;
  background: linear-gradient(145deg, #2c3e50, #34495e);
  border-radius: 25px;
  padding: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
}
```

**الشرح:**

- `width: 200px; height: 350px`: أبعاد الهاتف
- `background: linear-gradient`: تدرج لوني للهاتف
- `border-radius: 25px`: زوايا مدورة مثل الهاتف الحقيقي
- `box-shadow`: ظل ثلاثي الأبعاد

### 4. الصور المصغرة

```css
.thumbnail {
  border: 2px solid transparent;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s;
  width: 80px;
  height: 80px;
}

.thumbnail:hover {
  border-color: #007185;
  transform: scale(1.05);
}
```

**الشرح:**

- `border: 2px solid transparent`: حدود شفافة
- `cursor: pointer`: مؤشر يد عند التمرير
- `transition: all 0.3s`: انتقال سلس
- `transform: scale(1.05)`: تكبير عند التمرير

---

## 💰 معلومات المنتج

### 1. السعر

```html
<div class="product-price">
  <div class="price-current">1,250,000 ليرة سورية</div>
  <div class="price-original">1,500,000 ليرة سورية</div>
  <div class="price-save">وفر 250,000 ليرة سورية (17%)</div>
</div>
```

### 2. CSS للسعر

```css
.price-current {
  font-size: 28px;
  font-weight: bold;
  color: #0f1111;
  margin-bottom: 5px;
}

.price-original {
  font-size: 16px;
  color: #565959;
  text-decoration: line-through;
  margin-bottom: 5px;
}

.price-save {
  font-size: 14px;
  color: #007600;
  font-weight: bold;
}
```

**الشرح:**

- `font-size: 28px`: حجم كبير للسعر الحالي
- `text-decoration: line-through`: خط في السعر الأصلي
- `color: #007600`: لون أخضر للتوفير

---

## 🎨 خيارات المنتج

### 1. خيارات الألوان

```html
<div class="color-options">
  <button
    class="color-option active"
    style="background-color: #8B7355;"
  ></button>
  <button class="color-option" style="background-color: #4A90E2;"></button>
</div>
```

### 2. CSS للألوان

```css
.color-option {
  width: 40px;
  height: 40px;
  border: 2px solid #ddd;
  border-radius: 50%;
  cursor: pointer;
  transition: all 0.3s;
}

.color-option:hover {
  border-color: #007185;
  transform: scale(1.1);
}

.color-option.active {
  border-color: #f0c14b;
  box-shadow: 0 0 0 2px #f0c14b;
}
```

**الشرح:**

- `width: 40px; height: 40px`: أبعاد دائرية
- `border-radius: 50%`: يجعلها دائرية
- `transform: scale(1.1)`: تكبير عند التمرير
- `box-shadow`: ظل للخيار النشط

---

## 🔘 الأزرار

### 1. أزرار الإجراءات

```html
<div class="product-actions">
  <button class="btn-add-to-cart">أضف للسلة</button>
  <button class="btn-buy-now">اشتري الآن</button>
  <button class="btn-wishlist">❤️ أضف للمفضلة</button>
</div>
```

### 2. CSS للأزرار

```css
.btn-add-to-cart,
.btn-buy-now,
.btn-wishlist {
  padding: 12px 24px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  transition: all 0.3s;
  flex: 1;
  min-width: 120px;
}

.btn-add-to-cart {
  background-color: #f0c14b;
  color: #131921;
}

.btn-add-to-cart:hover {
  background-color: #ddb347;
}
```

**الشرح:**

- `padding: 12px 24px`: مسافة داخلية
- `border-radius: 8px`: زوايا مدورة
- `transition: all 0.3s`: انتقال سلس
- `flex: 1`: يأخذ مساحة متساوية

---

## 📝 النماذج

### 1. نظام Checkbox للنماذج

```html
<input type="checkbox" id="loginTrigger" class="modal-trigger" />
<div id="loginModal" class="modal">
  <div class="modal-content">
    <label for="loginTrigger" class="close">&times;</label>
    <!-- محتوى النموذج -->
  </div>
</div>
```

### 2. CSS للنماذج

```css
.modal-trigger {
  display: none;
}

.modal-trigger:checked + .modal {
  display: block;
}

.modal {
  display: none;
  position: fixed;
  z-index: 2000;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
}
```

**الشرح:**

- `display: none`: يخفي الـ checkbox
- `:checked + .modal`: يظهر النموذج عند تفعيل الـ checkbox
- `position: fixed`: يثبت النموذج في مكانه
- `background-color: rgba(0,0,0,0.5)`: خلفية شفافة

### 3. محتوى النموذج

```css
.modal-content {
  background-color: white;
  margin: 5% auto;
  padding: 0;
  border-radius: 12px;
  width: 90%;
  max-width: 500px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  animation: modalSlideIn 0.3s ease-out;
}
```

**الشرح:**

- `margin: 5% auto`: يوسط النموذج
- `border-radius: 12px`: زوايا مدورة
- `box-shadow`: ظل جميل
- `animation`: تأثير انزلاق

---

## 📱 التصميم المتجاوب

### 1. Media Queries

```css
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

@media (max-width: 480px) {
  .container {
    padding: 0 10px;
  }

  .product-title {
    font-size: 18px;
  }
}
```

**الشرح:**

- `@media (max-width: 768px)`: للأجهزة اللوحية
- `@media (max-width: 480px)`: للهواتف
- `grid-template-columns: 1fr`: عمود واحد للهواتف
- `flex-direction: column`: ترتيب عمودي

---

## 🎭 التأثيرات والانتقالات

### 1. CSS Transitions

```css
.btn-add-to-cart {
  transition: all 0.3s;
}

.btn-add-to-cart:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}
```

**الشرح:**

- `transition: all 0.3s`: انتقال سلس لجميع الخصائص
- `transform: translateY(-2px)`: حركة لأعلى
- `box-shadow`: ظل عند التمرير

### 2. CSS Animations

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

**الشرح:**

- `@keyframes`: يحدد مراحل الحركة
- `from`: الحالة الأولية
- `to`: الحالة النهائية
- `animation`: يطبق الحركة

---

## 🔍 إمكانية الوصول

### 1. Focus States

```css
button:focus,
input:focus,
a:focus {
  outline: 2px solid #007185;
  outline-offset: 2px;
}
```

**الشرح:**

- `outline`: حدود واضحة عند التركيز
- `outline-offset`: مسافة من العنصر

### 2. Semantic HTML

```html
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

---

## 🌐 دعم اللغات

### 1. الصفحة العربية

```html
<html lang="ar" dir="rtl"></html>
```

### 2. الصفحة الإنجليزية

```html
<html lang="en" dir="ltr"></html>
```

### 3. التبديل بين اللغات

```html
<a href="index-en.html" class="language-link">
  <span class="flag">🇺🇸</span>
  <span>English</span>
</a>
```

---

## 🎯 أفضل الممارسات المستخدمة

### 1. CSS Organization

- تجميع القواعد المتشابهة
- استخدام تعليقات واضحة
- ترتيب منطقي للخصائص

### 2. HTML Structure

- استخدام العناصر الدلالية
- ترتيب منطقي للمحتوى
- إضافة attributes مناسبة

### 3. Performance

- CSS محسن
- صور متجاوبة
- انتقالات سلسة

---

## 🔧 نصائح للتطوير

### 1. Debugging

```css
/* إضافة حدود مؤقتة للتصحيح */
.debug {
  border: 1px solid red !important;
}
```

### 2. Testing

- اختبار في متصفحات مختلفة
- اختبار على أجهزة مختلفة
- اختبار إمكانية الوصول

### 3. Maintenance

- تعليقات واضحة في الكود
- تنظيم الملفات
- توثيق التغييرات

---

## 📚 المراجع

### 1. CSS Properties

- [MDN CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

### 2. HTML Elements

- [MDN HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [HTML5 Semantic Elements](https://www.w3schools.com/html/html5_semantic_elements.asp)

### 3. Accessibility

- [WCAG Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WebAIM](https://webaim.org/)

---

## 🎉 الخلاصة

هذا الدليل يوضح كل تفصيل في الكود المستخدم في المشروع. كل CSS class وكل HTML element له غرض محدد وواضح. المشروع يتبع أفضل الممارسات في التطوير ويوفر تجربة مستخدم ممتازة.

**المشروع جاهز للاستخدام والتطوير!** 🚀
