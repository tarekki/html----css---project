# 🚀 دليل النشر والتوزيع - مشروع صفحة منتجات أمازون

## 🎯 نظرة عامة

هذا الدليل يوضح كيفية نشر المشروع وتوزيعه على منصات مختلفة، مع خطوات مفصلة وأمثلة عملية.

---

## 📋 خيارات النشر

### 1. النشر المجاني

- [ ] GitHub Pages
- [ ] Netlify
- [ ] Vercel
- [ ] Firebase Hosting

### 2. النشر المدفوع

- [ ] AWS S3 + CloudFront
- [ ] Google Cloud Storage
- [ ] Azure Static Web Apps
- [ ] DigitalOcean Spaces

### 3. النشر المحلي

- [ ] خادم محلي
- [ ] خادم VPS
- [ ] خادم مخصص

---

## 🌐 النشر على GitHub Pages

### 1. إعداد Repository

#### إنشاء Repository جديد

```bash
# إنشاء مجلد جديد
mkdir amazon-product-page
cd amazon-product-page

# تهيئة Git
git init

# إضافة الملفات
git add .
git commit -m "Initial commit: Amazon product page"

# ربط بالـ Repository
git remote add origin https://github.com/username/amazon-product-page.git
git branch -M main
git push -u origin main
```

#### إعداد GitHub Pages

1. اذهب إلى **Settings** في Repository
2. اختر **Pages** من القائمة الجانبية
3. في **Source**، اختر **Deploy from a branch**
4. اختر **Branch: main**
5. اختر **Folder: / (root)**
6. اضغط **Save**

### 2. إعداد الملفات

#### إضافة ملف .gitignore

```gitignore
# ملفات النظام
.DS_Store
Thumbs.db

# ملفات التطوير
.vscode/
.idea/
*.log

# ملفات مؤقتة
*.tmp
*.temp

# ملفات النسخ الاحتياطي
*.bak
*.backup
```

#### إضافة ملف README.md

````markdown
# 🛒 صفحة منتجات أمازون

صفحة منتجات أمازون احترافية تم تطويرها باستخدام HTML و CSS فقط.

## 🌐 الموقع المباشر

[عرض الموقع](https://username.github.io/amazon-product-page)

## 📱 الميزات

- تصميم متجاوب
- دعم اللغتين العربية والإنجليزية
- نماذج تفاعلية
- تصميم احترافي

## 🚀 التشغيل المحلي

```bash
git clone https://github.com/username/amazon-product-page.git
cd amazon-product-page
open index.html
```
````

````

### 3. النشر التلقائي

#### إضافة GitHub Actions
```yaml
# .github/workflows/deploy.yml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./
````

---

## 🌟 النشر على Netlify

### 1. النشر المباشر

#### رفع الملفات

1. اذهب إلى [Netlify](https://netlify.com)
2. اضغط **New site from Git**
3. اختر **GitHub** واربط حسابك
4. اختر Repository
5. اضغط **Deploy site**

#### إعدادات النشر

```toml
# netlify.toml
[build]
  publish = "."
  command = "echo 'No build step required'"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200

[build.environment]
  NODE_VERSION = "18"
```

### 2. النشر من المجلد

#### سحب الملفات

1. اذهب إلى [Netlify](https://netlify.com)
2. اضغط **New site from files**
3. اسحب مجلد المشروع
4. اضغط **Deploy site**

### 3. إعدادات متقدمة

#### إضافة Domain مخصص

1. اذهب إلى **Domain settings**
2. اضغط **Add custom domain**
3. أدخل اسم النطاق
4. اتبع التعليمات لإعداد DNS

#### إعدادات الأمان

```toml
# netlify.toml
[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-XSS-Protection = "1; mode=block"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"
```

---

## ⚡ النشر على Vercel

### 1. النشر من GitHub

#### ربط Repository

1. اذهب إلى [Vercel](https://vercel.com)
2. اضغط **New Project**
3. اختر **Import Git Repository**
4. اختر Repository
5. اضغط **Deploy**

#### إعدادات النشر

```json
// vercel.json
{
  "version": 2,
  "builds": [
    {
      "src": "**/*",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/$1"
    }
  ]
}
```

### 2. النشر من المجلد

#### استخدام Vercel CLI

```bash
# تثبيت Vercel CLI
npm i -g vercel

# النشر
vercel

# النشر للإنتاج
vercel --prod
```

---

## 🔥 النشر على Firebase Hosting

### 1. إعداد Firebase

#### تثبيت Firebase CLI

```bash
# تثبيت Firebase CLI
npm install -g firebase-tools

# تسجيل الدخول
firebase login

# تهيئة المشروع
firebase init hosting
```

#### إعداد firebase.json

```json
{
  "hosting": {
    "public": ".",
    "ignore": ["firebase.json", "**/.*", "**/node_modules/**"],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
}
```

### 2. النشر

#### النشر الأول

```bash
# النشر
firebase deploy

# النشر مع رسالة
firebase deploy --message "Initial deployment"
```

#### النشر التلقائي

```bash
# إضافة script في package.json
{
  "scripts": {
    "deploy": "firebase deploy"
  }
}
```

---

## ☁️ النشر على AWS S3

### 1. إعداد S3 Bucket

#### إنشاء Bucket

1. اذهب إلى [AWS Console](https://console.aws.amazon.com)
2. اختر **S3**
3. اضغط **Create bucket**
4. أدخل اسم Bucket
5. اختر **Public access**
6. اضغط **Create bucket**

#### إعداد Static Website Hosting

1. اختر Bucket
2. اذهب إلى **Properties**
3. اختر **Static website hosting**
4. اختر **Enable**
5. أدخل **index.html** كـ Index document
6. اضغط **Save**

### 2. رفع الملفات

#### استخدام AWS CLI

```bash
# تثبيت AWS CLI
pip install awscli

# إعداد الـ credentials
aws configure

# رفع الملفات
aws s3 sync . s3://your-bucket-name --delete
```

#### استخدام AWS Console

1. اختر Bucket
2. اضغط **Upload**
3. اسحب الملفات
4. اضغط **Upload**

### 3. إعداد CloudFront

#### إنشاء Distribution

1. اذهب إلى **CloudFront**
2. اضغط **Create Distribution**
3. اختر **Web**
4. أدخل **Origin Domain Name**
5. اختر **Default Root Object: index.html**
6. اضغط **Create Distribution**

---

## 🌐 النشر على خادم محلي

### 1. استخدام Python

#### خادم HTTP بسيط

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

#### الوصول للموقع

```
http://localhost:8000
```

### 2. استخدام Node.js

#### تثبيت http-server

```bash
# تثبيت http-server
npm install -g http-server

# تشغيل الخادم
http-server -p 8000
```

#### الوصول للموقع

```
http://localhost:8000
```

### 3. استخدام Apache

#### إعداد Virtual Host

```apache
# /etc/apache2/sites-available/amazon-product-page.conf
<VirtualHost *:80>
    ServerName amazon-product-page.local
    DocumentRoot /var/www/amazon-product-page

    <Directory /var/www/amazon-product-page>
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

#### تفعيل الموقع

```bash
# تفعيل الموقع
sudo a2ensite amazon-product-page.conf

# إعادة تشغيل Apache
sudo systemctl restart apache2
```

---

## 📱 النشر على الأجهزة المحمولة

### 1. إعداد PWA

#### إضافة manifest.json

```json
{
  "name": "Amazon Product Page",
  "short_name": "Amazon",
  "description": "صفحة منتجات أمازون",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#f8f9fa",
  "theme_color": "#f0c14b",
  "icons": [
    {
      "src": "icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "icon-512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ]
}
```

#### إضافة Service Worker

```javascript
// sw.js
const CACHE_NAME = "amazon-product-page-v1";
const urlsToCache = [
  "/",
  "/index.html",
  "/index-en.html",
  "/style.css",
  "/manifest.json",
];

self.addEventListener("install", function (event) {
  event.waitUntil(
    caches.open(CACHE_NAME).then(function (cache) {
      return cache.addAll(urlsToCache);
    })
  );
});

self.addEventListener("fetch", function (event) {
  event.respondWith(
    caches.match(event.request).then(function (response) {
      if (response) {
        return response;
      }
      return fetch(event.request);
    })
  );
});
```

### 2. إضافة Meta Tags

#### Meta Tags للأجهزة المحمولة

```html
<!-- في <head> -->
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="theme-color" content="#f0c14b" />
<meta name="apple-mobile-web-app-capable" content="yes" />
<meta name="apple-mobile-web-app-status-bar-style" content="default" />
<meta name="apple-mobile-web-app-title" content="Amazon" />

<!-- روابط PWA -->
<link rel="manifest" href="/manifest.json" />
<link rel="apple-touch-icon" href="/icon-192.png" />
```

---

## 🔧 تحسين الأداء

### 1. ضغط الملفات

#### ضغط CSS

```bash
# تثبيت cssnano
npm install -g cssnano

# ضغط CSS
cssnano style.css style.min.css
```

#### ضغط HTML

```bash
# تثبيت html-minifier
npm install -g html-minifier

# ضغط HTML
html-minifier --collapse-whitespace --remove-comments --minify-js index.html -o index.min.html
```

### 2. تحسين الصور

#### تحويل الصور

```bash
# تثبيت imagemin
npm install -g imagemin-cli

# تحسين الصور
imagemin images/* --out-dir=images/optimized
```

#### استخدام WebP

```html
<picture>
  <source srcset="image.webp" type="image/webp" />
  <img src="image.jpg" alt="Product Image" />
</picture>
```

### 3. إعدادات الخادم

#### إعدادات Apache

```apache
# .htaccess
# ضغط الملفات
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/plain
    AddOutputFilterByType DEFLATE text/html
    AddOutputFilterByType DEFLATE text/xml
    AddOutputFilterByType DEFLATE text/css
    AddOutputFilterByType DEFLATE application/xml
    AddOutputFilterByType DEFLATE application/xhtml+xml
    AddOutputFilterByType DEFLATE application/rss+xml
    AddOutputFilterByType DEFLATE application/javascript
    AddOutputFilterByType DEFLATE application/x-javascript
</IfModule>

# Cache Headers
<IfModule mod_expires.c>
    ExpiresActive on
    ExpiresByType text/css "access plus 1 year"
    ExpiresByType application/javascript "access plus 1 year"
    ExpiresByType image/png "access plus 1 year"
    ExpiresByType image/jpg "access plus 1 year"
    ExpiresByType image/jpeg "access plus 1 year"
</IfModule>
```

#### إعدادات Nginx

```nginx
# nginx.conf
server {
    listen 80;
    server_name your-domain.com;
    root /var/www/amazon-product-page;
    index index.html;

    # ضغط الملفات
    gzip on;
    gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;

    # Cache Headers
    location ~* \.(css|js|png|jpg|jpeg|gif|ico|svg)$ {
        expires 1y;
        add_header Cache-Control "public, immutable";
    }

    # Fallback للـ SPA
    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

---

## 🔍 مراقبة الأداء

### 1. أدوات المراقبة

#### Google Analytics

```html
<!-- في <head> -->
<script
  async
  src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"
></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag() {
    dataLayer.push(arguments);
  }
  gtag("js", new Date());
  gtag("config", "GA_MEASUREMENT_ID");
</script>
```

#### Google PageSpeed Insights

```html
<!-- في <head> -->
<script>
  // تتبع Core Web Vitals
  function sendToAnalytics(metric) {
    gtag("event", metric.name, {
      value: Math.round(metric.value),
      event_category: "Web Vitals",
      event_label: metric.id,
      non_interaction: true,
    });
  }
</script>
```

### 2. مراقبة الأخطاء

#### Sentry

```html
<!-- في <head> -->
<script src="https://browser.sentry-cdn.com/7.0.0/bundle.min.js"></script>
<script>
  Sentry.init({
    dsn: "YOUR_DSN_HERE",
    environment: "production",
  });
</script>
```

---

## 🚀 النشر التلقائي

### 1. GitHub Actions

#### إعداد CI/CD

```yaml
# .github/workflows/deploy.yml
name: Deploy to Production

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v2

      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: "18"

      - name: Install dependencies
        run: npm install

      - name: Build project
        run: npm run build

      - name: Deploy to Netlify
        uses: nwtgck/actions-netlify@v1.2
        with:
          publish-dir: "./dist"
          production-branch: main
          github-token: ${{ secrets.GITHUB_TOKEN }}
          deploy-message: "Deploy from GitHub Actions"
        env:
          NETLIFY_AUTH_TOKEN: ${{ secrets.NETLIFY_AUTH_TOKEN }}
          NETLIFY_SITE_ID: ${{ secrets.NETLIFY_SITE_ID }}
```

### 2. Netlify Build Hooks

#### إعداد Build Hook

1. اذهب إلى **Site settings**
2. اختر **Build & deploy**
3. اضغط **Build hooks**
4. اضغط **Add build hook**
5. أدخل اسم واختر branch
6. اضغط **Save**

#### استخدام Build Hook

```bash
# تشغيل Build Hook
curl -X POST -d {} https://api.netlify.com/build_hooks/YOUR_BUILD_HOOK_ID
```

---

## 🎯 الخلاصة

هذا الدليل يوضح جميع طرق النشر المتاحة للمشروع. اختر الطريقة المناسبة لاحتياجاتك وميزانيتك.

**استخدم هذا الدليل لنشر مشروعك بنجاح!** 🚀

---

**تم إنشاء هذا الملف بواسطة:** Tarek al sabbagh
**التاريخ:** 2025
**الإصدار:** 1.0.0
