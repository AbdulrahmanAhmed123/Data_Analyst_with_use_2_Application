# Data_Analyst_with_use_2_Application
# Web Scraping & Financial Data Retrieval API 🚀

هذا المشروع مقسم لجزئين أساسيين بيوضحوا إزاي نقدر نجمع البيانات من الويب بأكثر من طريقة: الأولى عن طريق **Web Scraping** لصفحات الـ HTML، والثانية عن طريق سحب بيانات مالية حية باستخدام **Financial APIs**.

---

## 📌 Features & Project Parts (محتويات المشروع)

### 1️⃣ Part 1: Web Scraping using BeautifulSoup & Requests
في الجزء ده، اشتغلنا على سحب وتجميع البيانات من موقع عيادة بيطرية تجريبي اسمه **Wisdom Pet Medicine**:
* **HTTP Requests**: استخدمنا مكتبة `requests` عشان نبعت `GET` request للموقع ونتأكد إن الـ `status_code` تمام (200 OK).
* **HTML Parsing**: استخدمنا مكتبة `BeautifulSoup` عشان نعمل `prettify` للـ HTML ونقدر نقرأ الـ Structure بتاعه بسهولة.
* **Data Extraction**:
    * سحبنا الـ `title` بتاع الصفحة.
    * استخرجنا أرقام التليفونات والـ classes المعينة زي (الـ spans والـ quotes).
    * عملنا Loop عشان نطلع بيانات الدكاترة والـ Staff مع الـ Testimonials (آراء العملاء) والروابط الموجودة في الصفحة.
* **File Export**: حفظنا الـ HTML المنظم في ملف خارجي باسم `wisdompetMedicie`.

### 2️⃣ Part 2: Financial Data Retrieval using Alpha Vantage API
الجزء الثاني مخصص للتعامل مع الـ Financial Data والـ APIs الحقيقية:
* **API Integration**: استخدمنا الـ API Key الخاص بمنصة **Alpha Vantage** لقراءة بيانات الأسهم.
* **Handling Rate Limits**: واجهنا الـ Rate limits العادية للـ Free API وطبقنا حلول ذكية لتجاوزها وسحب البيانات بصيغة **CSV**.
* **Data manipulation with Pandas**:
    * بعتنا Request مخصص لسحب بيانات أسهم شركة آبل (**AAPL**) التاريخية `TIME_SERIES_WEEKLY`.
    * حولنا الـ Response المرجع بصيغة الـ Bytes والـ CSV إلى **Pandas DataFrame** عشان نقدر نعملها تحليل بسهولة.
    * عرضنا أول كام صف من البيانات (`data.head()`) عشان نشوف الـ `open`, `high`, `low`, `close`, والـ `volume`.

---

## 🛠️ Tech Stack (الأدوات المستخدمة)

* **Python 3.x**
* **Requests**: لعقد الاتصال وإرسال الـ HTTP requests.
* **BeautifulSoup4 (bs4)**: لعمل parse واستخراج البيانات من الـ HTML text.
* **Alpha Vantage**: المكتبة والـ API المخصصة لبيانات البورصة والأسهم.
* **Pandas**: لتنظيم البيانات وتحويلها لـ DataFrames سهلة القراءة والتحليل.
* **IO**: للتعامل مع الـ String data وتحويلها لـ File-like object للـ Pandas.

---

## 🚀 How to Run (طريقة التشغيل)

1. اعمل Clone للـ Repository عندك:
```bash
   git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
طبعاً كل المكتبات دي موجودة في أول الـ Notebook وجاهزة للـ Install:

Python
   %pip install requests bs4 alpha_vantage pandas
افتح ملف الـ Jupyter Notebook أو الـ Colab واعمل Run All Cells
