# 🚀 دليل إضافة الميزات - مشروع صفحة منتجات أمازون

## 🎯 نظرة عامة

هذا الدليل يوضح كيفية إضافة ميزات جديدة للمشروع، مع أمثلة عملية وتوضيحات مفصلة.

---

## 📋 قائمة الميزات المقترحة

### 1. ميزات أساسية

- [ ] نظام البحث
- [ ] تصفية المنتجات
- [ ] مقارنة المنتجات
- [ ] نظام التقييمات
- [ ] نظام المفضلة
- [ ] نظام السلة

### 2. ميزات متقدمة

- [ ] نظام المستخدمين
- [ ] نظام الطلبات
- [ ] نظام الدفع
- [ ] نظام التوصيل
- [ ] نظام الدعم الفني

### 3. ميزات إضافية

- [ ] نظام الإشعارات
- [ ] نظام التوصيات
- [ ] نظام الخصومات
- [ ] نظام العضويات
- [ ] نظام الشركاء

---

## 🔍 إضافة نظام البحث

### 1. HTML للبحث

#### إضافة حقل البحث

```html
<!-- في الهيدر -->
<div class="search-bar">
  <form class="search-form" id="searchForm">
    <select class="search-category" id="searchCategory">
      <option value="all">جميع الفئات</option>
      <option value="electronics">الإلكترونيات</option>
      <option value="clothing">الملابس</option>
      <option value="home">المنزل</option>
    </select>
    <input
      type="text"
      id="searchInput"
      placeholder="ابحث عن منتج..."
      class="search-input"
    />
    <button type="submit" class="search-btn">🔍</button>
  </form>
</div>
```

#### إضافة نتائج البحث

```html
<!-- بعد الهيدر -->
<div class="search-results" id="searchResults" style="display: none;">
  <div class="container">
    <div class="search-header">
      <h2>نتائج البحث</h2>
      <span class="results-count"
        >تم العثور على <span id="resultsCount">0</span> منتج</span
      >
    </div>
    <div class="results-grid" id="resultsGrid">
      <!-- نتائج البحث ستظهر هنا -->
    </div>
  </div>
</div>
```

### 2. CSS للبحث

#### تنسيق نتائج البحث

```css
/* نتائج البحث */
.search-results {
  background-color: var(--bg-primary);
  padding: 30px 0;
  border-bottom: 1px solid var(--border-light);
}

.search-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
}

.results-count {
  color: var(--text-secondary);
  font-size: var(--font-sm);
}

.results-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
}

/* بطاقة المنتج في النتائج */
.result-card {
  background-color: var(--bg-secondary);
  border-radius: var(--radius-lg);
  padding: 20px;
  box-shadow: var(--shadow-sm);
  transition: var(--transition-normal);
  cursor: pointer;
}

.result-card:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-2px);
}

.result-card img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: var(--radius-md);
  margin-bottom: 15px;
}

.result-card h3 {
  font-size: var(--font-lg);
  margin-bottom: 10px;
  color: var(--text-primary);
}

.result-card .price {
  font-size: var(--font-xl);
  font-weight: var(--font-bold);
  color: var(--amazon-orange);
  margin-bottom: 10px;
}

.result-card .rating {
  display: flex;
  align-items: center;
  gap: 5px;
  margin-bottom: 15px;
}

.result-card .stars {
  color: #ffc107;
}

.result-card .rating-count {
  color: var(--text-secondary);
  font-size: var(--font-sm);
}
```

### 3. JavaScript للبحث

#### وظائف البحث

```javascript
// بيانات المنتجات (يمكن استبدالها بقاعدة بيانات)
const products = [
  {
    id: 1,
    name: "iPhone 15 Pro Max",
    category: "electronics",
    price: 1250000,
    rating: 4.8,
    ratingCount: 2847,
    image: "iphone.jpg",
  },
  {
    id: 2,
    name: "Samsung Galaxy S24",
    category: "electronics",
    price: 1100000,
    rating: 4.6,
    ratingCount: 1923,
    image: "samsung.jpg",
  },
  // المزيد من المنتجات...
];

// وظيفة البحث
function searchProducts(query, category) {
  let results = products;

  // تصفية حسب الفئة
  if (category !== "all") {
    results = results.filter((product) => product.category === category);
  }

  // تصفية حسب النص
  if (query) {
    results = results.filter((product) =>
      product.name.toLowerCase().includes(query.toLowerCase())
    );
  }

  return results;
}

// عرض النتائج
function displayResults(results) {
  const resultsGrid = document.getElementById("resultsGrid");
  const resultsCount = document.getElementById("resultsCount");
  const searchResults = document.getElementById("searchResults");

  if (results.length === 0) {
    resultsGrid.innerHTML = "<p>لم يتم العثور على منتجات</p>";
  } else {
    resultsGrid.innerHTML = results
      .map(
        (product) => `
            <div class="result-card" onclick="viewProduct(${product.id})">
                <img src="${product.image}" alt="${product.name}">
                <h3>${product.name}</h3>
                <div class="price">${product.price.toLocaleString()} ليرة سورية</div>
                <div class="rating">
                    <span class="stars">${"⭐".repeat(
                      Math.floor(product.rating)
                    )}</span>
                    <span class="rating-count">(${product.ratingCount})</span>
                </div>
            </div>
        `
      )
      .join("");
  }

  resultsCount.textContent = results.length;
  searchResults.style.display = "block";
}

// معالج البحث
document.getElementById("searchForm").addEventListener("submit", function (e) {
  e.preventDefault();

  const query = document.getElementById("searchInput").value;
  const category = document.getElementById("searchCategory").value;

  const results = searchProducts(query, category);
  displayResults(results);
});
```

---

## 🏷️ إضافة نظام التصفية

### 1. HTML للتصفية

#### إضافة أزرار التصفية

```html
<!-- بعد نتائج البحث -->
<div class="filters-section">
  <div class="container">
    <div class="filters-header">
      <h3>تصفية النتائج</h3>
      <button class="clear-filters" onclick="clearFilters()">
        مسح الفلاتر
      </button>
    </div>

    <div class="filters-grid">
      <!-- تصفية السعر -->
      <div class="filter-group">
        <h4>السعر</h4>
        <div class="price-range">
          <input
            type="range"
            id="priceMin"
            min="0"
            max="2000000"
            value="0"
            class="price-slider"
          />
          <input
            type="range"
            id="priceMax"
            min="0"
            max="2000000"
            value="2000000"
            class="price-slider"
          />
          <div class="price-labels">
            <span id="priceMinLabel">0</span>
            <span id="priceMaxLabel">2,000,000</span>
          </div>
        </div>
      </div>

      <!-- تصفية التقييم -->
      <div class="filter-group">
        <h4>التقييم</h4>
        <div class="rating-filters">
          <label class="rating-filter">
            <input type="checkbox" value="5" onchange="applyFilters()" />
            <span class="stars">⭐⭐⭐⭐⭐</span>
            <span>5 نجوم</span>
          </label>
          <label class="rating-filter">
            <input type="checkbox" value="4" onchange="applyFilters()" />
            <span class="stars">⭐⭐⭐⭐</span>
            <span>4 نجوم وأكثر</span>
          </label>
          <label class="rating-filter">
            <input type="checkbox" value="3" onchange="applyFilters()" />
            <span class="stars">⭐⭐⭐</span>
            <span>3 نجوم وأكثر</span>
          </label>
        </div>
      </div>

      <!-- تصفية العلامة التجارية -->
      <div class="filter-group">
        <h4>العلامة التجارية</h4>
        <div class="brand-filters">
          <label class="brand-filter">
            <input type="checkbox" value="apple" onchange="applyFilters()" />
            <span>Apple</span>
          </label>
          <label class="brand-filter">
            <input type="checkbox" value="samsung" onchange="applyFilters()" />
            <span>Samsung</span>
          </label>
          <label class="brand-filter">
            <input type="checkbox" value="huawei" onchange="applyFilters()" />
            <span>Huawei</span>
          </label>
        </div>
      </div>
    </div>
  </div>
</div>
```

### 2. CSS للتصفية

#### تنسيق التصفية

```css
/* قسم التصفية */
.filters-section {
  background-color: var(--bg-secondary);
  padding: 30px 0;
  border-bottom: 1px solid var(--border-light);
}

.filters-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
}

.filters-header h3 {
  font-size: var(--font-xl);
  color: var(--text-primary);
}

.clear-filters {
  background-color: var(--amazon-orange);
  color: var(--amazon-dark);
  border: none;
  padding: var(--padding-sm);
  border-radius: var(--radius-md);
  cursor: pointer;
  font-weight: var(--font-bold);
  transition: var(--transition-normal);
}

.clear-filters:hover {
  background-color: var(--hover);
}

.filters-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 30px;
}

.filter-group {
  background-color: var(--bg-primary);
  padding: 20px;
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-sm);
}

.filter-group h4 {
  font-size: var(--font-lg);
  margin-bottom: 15px;
  color: var(--text-primary);
}

/* تصفية السعر */
.price-range {
  position: relative;
}

.price-slider {
  width: 100%;
  height: 6px;
  border-radius: 3px;
  background: var(--border-light);
  outline: none;
  margin: 10px 0;
}

.price-slider::-webkit-slider-thumb {
  appearance: none;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: var(--amazon-orange);
  cursor: pointer;
}

.price-labels {
  display: flex;
  justify-content: space-between;
  font-size: var(--font-sm);
  color: var(--text-secondary);
}

/* تصفية التقييم */
.rating-filters {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.rating-filter {
  display: flex;
  align-items: center;
  gap: 10px;
  cursor: pointer;
  padding: 5px;
  border-radius: var(--radius-sm);
  transition: var(--transition-normal);
}

.rating-filter:hover {
  background-color: var(--bg-light);
}

.rating-filter input[type="checkbox"] {
  margin: 0;
}

/* تصفية العلامة التجارية */
.brand-filters {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.brand-filter {
  display: flex;
  align-items: center;
  gap: 10px;
  cursor: pointer;
  padding: 5px;
  border-radius: var(--radius-sm);
  transition: var(--transition-normal);
}

.brand-filter:hover {
  background-color: var(--bg-light);
}

.brand-filter input[type="checkbox"] {
  margin: 0;
}
```

### 3. JavaScript للتصفية

#### وظائف التصفية

```javascript
// وظيفة تطبيق الفلاتر
function applyFilters() {
  const priceMin = document.getElementById("priceMin").value;
  const priceMax = document.getElementById("priceMax").value;
  const ratingFilters = Array.from(
    document.querySelectorAll(".rating-filters input:checked")
  ).map((cb) => parseInt(cb.value));
  const brandFilters = Array.from(
    document.querySelectorAll(".brand-filters input:checked")
  ).map((cb) => cb.value);

  let filteredProducts = products;

  // تصفية السعر
  filteredProducts = filteredProducts.filter(
    (product) => product.price >= priceMin && product.price <= priceMax
  );

  // تصفية التقييم
  if (ratingFilters.length > 0) {
    filteredProducts = filteredProducts.filter((product) =>
      ratingFilters.some((rating) => product.rating >= rating)
    );
  }

  // تصفية العلامة التجارية
  if (brandFilters.length > 0) {
    filteredProducts = filteredProducts.filter((product) =>
      brandFilters.includes(product.brand)
    );
  }

  displayResults(filteredProducts);
}

// وظيفة مسح الفلاتر
function clearFilters() {
  document.getElementById("priceMin").value = 0;
  document.getElementById("priceMax").value = 2000000;
  document
    .querySelectorAll(".rating-filters input")
    .forEach((cb) => (cb.checked = false));
  document
    .querySelectorAll(".brand-filters input")
    .forEach((cb) => (cb.checked = false));

  displayResults(products);
}

// تحديث تسميات السعر
document.getElementById("priceMin").addEventListener("input", function () {
  document.getElementById("priceMinLabel").textContent =
    this.value.toLocaleString();
  applyFilters();
});

document.getElementById("priceMax").addEventListener("input", function () {
  document.getElementById("priceMaxLabel").textContent =
    this.value.toLocaleString();
  applyFilters();
});
```

---

## ⭐ إضافة نظام التقييمات

### 1. HTML للتقييمات

#### إضافة قسم التقييمات

```html
<!-- بعد معلومات المنتج -->
<section class="reviews-section">
  <div class="container">
    <div class="reviews-header">
      <h2>تقييمات العملاء</h2>
      <button class="write-review-btn" onclick="openReviewModal()">
        اكتب تقييماً
      </button>
    </div>

    <div class="reviews-summary">
      <div class="rating-overview">
        <div class="average-rating">
          <span class="rating-number">4.8</span>
          <div class="stars">⭐⭐⭐⭐⭐</div>
          <span class="rating-count">2,847 تقييم</span>
        </div>
        <div class="rating-breakdown">
          <div class="rating-bar">
            <span>5 ⭐</span>
            <div class="bar">
              <div class="fill" style="width: 85%"></div>
            </div>
            <span>85%</span>
          </div>
          <div class="rating-bar">
            <span>4 ⭐</span>
            <div class="bar">
              <div class="fill" style="width: 12%"></div>
            </div>
            <span>12%</span>
          </div>
          <div class="rating-bar">
            <span>3 ⭐</span>
            <div class="bar">
              <div class="fill" style="width: 2%"></div>
            </div>
            <span>2%</span>
          </div>
          <div class="rating-bar">
            <span>2 ⭐</span>
            <div class="bar">
              <div class="fill" style="width: 1%"></div>
            </div>
            <span>1%</span>
          </div>
          <div class="rating-bar">
            <span>1 ⭐</span>
            <div class="bar">
              <div class="fill" style="width: 0%"></div>
            </div>
            <span>0%</span>
          </div>
        </div>
      </div>
    </div>

    <div class="reviews-list">
      <div class="review-item">
        <div class="review-header">
          <div class="reviewer-info">
            <div class="reviewer-avatar">👤</div>
            <div class="reviewer-details">
              <h4>أحمد محمد</h4>
              <span class="review-date">15 يناير 2025</span>
            </div>
          </div>
          <div class="review-rating">
            <span class="stars">⭐⭐⭐⭐⭐</span>
          </div>
        </div>
        <div class="review-content">
          <h5>منتج ممتاز</h5>
          <p>هذا المنتج رائع جداً، الجودة عالية والسعر مناسب. أنصح به بشدة.</p>
        </div>
        <div class="review-helpful">
          <button class="helpful-btn">👍 مفيد (15)</button>
          <button class="not-helpful-btn">👎 غير مفيد (2)</button>
        </div>
      </div>

      <!-- المزيد من التقييمات... -->
    </div>

    <div class="load-more-reviews">
      <button class="load-more-btn">عرض المزيد من التقييمات</button>
    </div>
  </div>
</section>
```

### 2. CSS للتقييمات

#### تنسيق التقييمات

```css
/* قسم التقييمات */
.reviews-section {
  background-color: var(--bg-primary);
  padding: 50px 0;
}

.reviews-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 40px;
}

.reviews-header h2 {
  font-size: var(--font-2xl);
  color: var(--text-primary);
}

.write-review-btn {
  background-color: var(--amazon-orange);
  color: var(--amazon-dark);
  border: none;
  padding: var(--padding-sm);
  border-radius: var(--radius-md);
  cursor: pointer;
  font-weight: var(--font-bold);
  transition: var(--transition-normal);
}

.write-review-btn:hover {
  background-color: var(--hover);
}

/* ملخص التقييمات */
.reviews-summary {
  background-color: var(--bg-secondary);
  padding: 30px;
  border-radius: var(--radius-lg);
  margin-bottom: 40px;
  box-shadow: var(--shadow-sm);
}

.rating-overview {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 40px;
  align-items: center;
}

.average-rating {
  text-align: center;
}

.rating-number {
  font-size: 48px;
  font-weight: var(--font-bold);
  color: var(--text-primary);
  display: block;
  margin-bottom: 10px;
}

.average-rating .stars {
  font-size: 24px;
  margin-bottom: 10px;
}

.rating-count {
  color: var(--text-secondary);
  font-size: var(--font-sm);
}

/* تفصيل التقييمات */
.rating-breakdown {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.rating-bar {
  display: flex;
  align-items: center;
  gap: 15px;
}

.rating-bar span:first-child {
  width: 40px;
  font-size: var(--font-sm);
}

.rating-bar span:last-child {
  width: 40px;
  text-align: right;
  font-size: var(--font-sm);
  color: var(--text-secondary);
}

.bar {
  flex: 1;
  height: 8px;
  background-color: var(--border-light);
  border-radius: 4px;
  overflow: hidden;
}

.bar .fill {
  height: 100%;
  background-color: var(--amazon-orange);
  transition: width 0.3s ease;
}

/* قائمة التقييمات */
.reviews-list {
  display: flex;
  flex-direction: column;
  gap: 30px;
  margin-bottom: 40px;
}

.review-item {
  background-color: var(--bg-secondary);
  padding: 25px;
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-sm);
}

.review-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}

.reviewer-info {
  display: flex;
  align-items: center;
  gap: 15px;
}

.reviewer-avatar {
  width: 50px;
  height: 50px;
  background-color: var(--amazon-orange);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
}

.reviewer-details h4 {
  font-size: var(--font-lg);
  color: var(--text-primary);
  margin-bottom: 5px;
}

.review-date {
  color: var(--text-secondary);
  font-size: var(--font-sm);
}

.review-rating .stars {
  font-size: 18px;
}

.review-content h5 {
  font-size: var(--font-lg);
  color: var(--text-primary);
  margin-bottom: 10px;
}

.review-content p {
  color: var(--text-secondary);
  line-height: 1.6;
  margin-bottom: 20px;
}

.review-helpful {
  display: flex;
  gap: 15px;
}

.helpful-btn,
.not-helpful-btn {
  background-color: transparent;
  border: 1px solid var(--border-light);
  padding: 8px 15px;
  border-radius: var(--radius-sm);
  cursor: pointer;
  font-size: var(--font-sm);
  transition: var(--transition-normal);
}

.helpful-btn:hover,
.not-helpful-btn:hover {
  background-color: var(--bg-light);
}

/* زر تحميل المزيد */
.load-more-reviews {
  text-align: center;
}

.load-more-btn {
  background-color: var(--amazon-blue);
  color: white;
  border: none;
  padding: var(--padding-sm);
  border-radius: var(--radius-md);
  cursor: pointer;
  font-weight: var(--font-bold);
  transition: var(--transition-normal);
}

.load-more-btn:hover {
  background-color: #005f6b;
}
```

---

## 🛒 إضافة نظام السلة

### 1. HTML للسلة

#### إضافة عربة التسوق

```html
<!-- في الهيدر -->
<div class="cart">
  <a href="#" class="cart-link" onclick="toggleCart()">
    <span class="cart-icon">🛒</span>
    <span class="cart-count" id="cartCount">0</span>
    <span class="cart-text">السلة</span>
  </a>
</div>

<!-- نافذة السلة -->
<div class="cart-modal" id="cartModal">
  <div class="cart-content">
    <div class="cart-header">
      <h3>سلة التسوق</h3>
      <button class="close-cart" onclick="toggleCart()">&times;</button>
    </div>

    <div class="cart-items" id="cartItems">
      <!-- عناصر السلة ستظهر هنا -->
    </div>

    <div class="cart-summary">
      <div class="cart-total">
        <span>المجموع:</span>
        <span id="cartTotal">0 ليرة سورية</span>
      </div>
      <button class="checkout-btn">الدفع</button>
    </div>
  </div>
</div>
```

### 2. CSS للسلة

#### تنسيق السلة

```css
/* نافذة السلة */
.cart-modal {
  position: fixed;
  top: 0;
  right: -400px;
  width: 400px;
  height: 100vh;
  background-color: var(--bg-secondary);
  box-shadow: var(--shadow-xl);
  transition: right 0.3s ease;
  z-index: 2000;
  overflow-y: auto;
}

.cart-modal.open {
  right: 0;
}

.cart-content {
  height: 100%;
  display: flex;
  flex-direction: column;
}

.cart-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  border-bottom: 1px solid var(--border-light);
}

.cart-header h3 {
  font-size: var(--font-xl);
  color: var(--text-primary);
}

.close-cart {
  background: none;
  border: none;
  font-size: 24px;
  cursor: pointer;
  color: var(--text-secondary);
}

.cart-items {
  flex: 1;
  padding: 20px;
}

.cart-item {
  display: flex;
  gap: 15px;
  padding: 15px 0;
  border-bottom: 1px solid var(--border-light);
}

.cart-item img {
  width: 80px;
  height: 80px;
  object-fit: cover;
  border-radius: var(--radius-md);
}

.cart-item-info {
  flex: 1;
}

.cart-item-info h4 {
  font-size: var(--font-base);
  color: var(--text-primary);
  margin-bottom: 5px;
}

.cart-item-info .price {
  font-size: var(--font-lg);
  font-weight: var(--font-bold);
  color: var(--amazon-orange);
  margin-bottom: 10px;
}

.cart-item-controls {
  display: flex;
  align-items: center;
  gap: 10px;
}

.quantity-btn {
  width: 30px;
  height: 30px;
  border: 1px solid var(--border-light);
  background-color: var(--bg-primary);
  cursor: pointer;
  border-radius: var(--radius-sm);
  display: flex;
  align-items: center;
  justify-content: center;
}

.quantity-input {
  width: 50px;
  text-align: center;
  border: 1px solid var(--border-light);
  border-radius: var(--radius-sm);
  padding: 5px;
}

.remove-item {
  background: none;
  border: none;
  color: var(--error);
  cursor: pointer;
  font-size: var(--font-sm);
}

.cart-summary {
  padding: 20px;
  border-top: 1px solid var(--border-light);
}

.cart-total {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  font-size: var(--font-xl);
  font-weight: var(--font-bold);
  color: var(--text-primary);
}

.checkout-btn {
  width: 100%;
  background-color: var(--amazon-orange);
  color: var(--amazon-dark);
  border: none;
  padding: var(--padding-md);
  border-radius: var(--radius-md);
  cursor: pointer;
  font-weight: var(--font-bold);
  font-size: var(--font-lg);
  transition: var(--transition-normal);
}

.checkout-btn:hover {
  background-color: var(--hover);
}

/* عداد السلة */
.cart-count {
  background-color: var(--amazon-orange);
  color: var(--amazon-dark);
  border-radius: 50%;
  width: 20px;
  height: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: var(--font-xs);
  font-weight: var(--font-bold);
  position: absolute;
  top: -5px;
  right: -5px;
}
```

### 3. JavaScript للسلة

#### وظائف السلة

```javascript
// بيانات السلة
let cart = [];

// وظيفة إضافة منتج للسلة
function addToCart(productId) {
  const product = products.find((p) => p.id === productId);
  if (!product) return;

  const existingItem = cart.find((item) => item.id === productId);
  if (existingItem) {
    existingItem.quantity += 1;
  } else {
    cart.push({
      ...product,
      quantity: 1,
    });
  }

  updateCartDisplay();
  showCartNotification();
}

// وظيفة تحديث عرض السلة
function updateCartDisplay() {
  const cartCount = document.getElementById("cartCount");
  const cartItems = document.getElementById("cartItems");
  const cartTotal = document.getElementById("cartTotal");

  // تحديث العداد
  const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
  cartCount.textContent = totalItems;

  // تحديث العناصر
  if (cart.length === 0) {
    cartItems.innerHTML = "<p>السلة فارغة</p>";
  } else {
    cartItems.innerHTML = cart
      .map(
        (item) => `
            <div class="cart-item">
                <img src="${item.image}" alt="${item.name}">
                <div class="cart-item-info">
                    <h4>${item.name}</h4>
                    <div class="price">${item.price.toLocaleString()} ليرة سورية</div>
                    <div class="cart-item-controls">
                        <button class="quantity-btn" onclick="updateQuantity(${
                          item.id
                        }, -1)">-</button>
                        <input type="number" class="quantity-input" value="${
                          item.quantity
                        }" min="1" onchange="setQuantity(${
          item.id
        }, this.value)">
                        <button class="quantity-btn" onclick="updateQuantity(${
                          item.id
                        }, 1)">+</button>
                        <button class="remove-item" onclick="removeFromCart(${
                          item.id
                        })">حذف</button>
                    </div>
                </div>
            </div>
        `
      )
      .join("");
  }

  // تحديث المجموع
  const total = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
  cartTotal.textContent = `${total.toLocaleString()} ليرة سورية`;
}

// وظيفة تحديث الكمية
function updateQuantity(productId, change) {
  const item = cart.find((item) => item.id === productId);
  if (item) {
    item.quantity += change;
    if (item.quantity <= 0) {
      removeFromCart(productId);
    } else {
      updateCartDisplay();
    }
  }
}

// وظيفة تعيين الكمية
function setQuantity(productId, quantity) {
  const item = cart.find((item) => item.id === productId);
  if (item) {
    item.quantity = parseInt(quantity);
    if (item.quantity <= 0) {
      removeFromCart(productId);
    } else {
      updateCartDisplay();
    }
  }
}

// وظيفة حذف منتج من السلة
function removeFromCart(productId) {
  cart = cart.filter((item) => item.id !== productId);
  updateCartDisplay();
}

// وظيفة تبديل السلة
function toggleCart() {
  const cartModal = document.getElementById("cartModal");
  cartModal.classList.toggle("open");
}

// وظيفة إشعار السلة
function showCartNotification() {
  // يمكن إضافة إشعار هنا
  console.log("تم إضافة المنتج للسلة");
}
```

---

## 🎯 الخلاصة

هذا الدليل يوضح كيفية إضافة ميزات جديدة للمشروع. كل ميزة مصممة لتكون متوافقة مع التصميم الحالي وتعمل بدون JavaScript (باستثناء الميزات التفاعلية).

**استخدم هذا الدليل لإضافة المزيد من الميزات!** 🚀

---

**تم إنشاء هذا الملف بواسطة:** Tarek al sabbagh
**التاريخ:** 2025
**الإصدار:** 1.0.0
