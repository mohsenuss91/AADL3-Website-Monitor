# AADL3 Website Monitor

## مقدمة

هذا المشروع يهدف إلى بناء نظام لمراقبة وتفاعل مع موقع الويب AADL3. النظام يمكن المستخدم من فتح عدة متصفحات، التحقق من حالة صفحات الويب، وأخذ لقطات شاشة للمراقبة. بالإضافة إلى ذلك، يتم إرسال تنبيهات عبر Telegram في حالة حدوث تغييرات في محتوى الصفحة.

## المتطلبات
### Windows:
1. **Node.js**: تحميل وتثبيت Node.js من [الرابط الرسمي](https://nodejs.org/).
2. **Git**: تحميل وتثبيت Git من [الرابط الرسمي](https://git-scm.com/).

### Linux (Ubuntu/Debian):
1. **Node.js**:
    ```bash
    sudo apt update
    sudo apt install nodejs
    sudo apt install npm
    ```
2. **Git**:
    ```bash
    sudo apt install git
    ```

## كيفية التثبيت والتشغيل
1. **تنزيل الكود**:
    ```bash
    git clone https://github.com/TerminalDZ/AADL3-Website-Monitor.git
    cd AADL3-Website-Monitor
    ```

2. **تثبيت التبعيات**:
    ```bash
    npm install
    ```

3. **تشغيل التطبيق**:
    ```bash
    node index.js
    ```

4. **الوصول إلى الواجهة**:
   افتح متصفح الإنترنت وانتقل إلى:
    ```
    http://localhost:3000
    ```

## ملفات المشروع
- **index.js**: الكود الرئيسي لتشغيل التطبيق.
- **public/**: الملفات الثابتة التي تخدم الواجهة الأمامية.
- **info.txt**: ملف البيانات لإدارة السجلات.

## كيفية الاستخدام
### بدء تشغيل متصفح جديد
1. اضغط على زر "Start New Browser".
2. اختر عدد المتصفحات (1-9).
3. اضغط على "Start".

### إيقاف جميع المتصفحات
اضغط على زر "Stop All Browsers".

### أخذ لقطات لجميع المتصفحات
اضغط على زر "Take All Screenshot".

### إدارة البيانات
1. اضغط على زر "Data Cards" لعرض السجلات.
2. لإضافة سجل جديد، اضغط على زر "Add Data" وأدخل البيانات.

### استعادة المتصفحات
يتم استعادة المتصفحات عند إعادة تحميل الصفحة تلقائيًا.

## كيفية إنشاء بوت Telegram والحصول على TELEGRAM_TOKEN و CHAT_ID
### إنشاء بوت Telegram:
1. افتح تطبيق Telegram وابحث عن المستخدم @BotFather.
2. ابدأ محادثة مع @BotFather وأرسل الأمر `/start`.
3. لإنشاء بوت جديد، أرسل الأمر `/newbot`.
4. اتبع التعليمات لتسمية البوت والحصول على اسم مستخدم (username) فريد له.
5. بعد إكمال الخطوات، ستحصل على رمز توكن البوت (API token). هذا هو `TELEGRAM_TOKEN`.

### الحصول على CHAT_ID:
1. افتح تطبيق Telegram وابحث عن البوت الذي قمت بإنشائه.
2. ابدأ محادثة مع البوت وأرسل أي رسالة.
3. افتح المتصفح وانتقل إلى الرابط التالي مع استبدال `TELEGRAM_TOKEN` برمز التوكن الخاص بك:
    ```
    https://api.telegram.org/bot<TELEGRAM_TOKEN>/getUpdates
    ```
4. ابحث في الاستجابة (response) عن `chat` وستجد `id`. هذا هو `CHAT_ID`.

## ملاحظات
- تأكد من ضبط متغيرات `TELEGRAM_TOKEN` و `CHAT_ID` بقيم صحيحة في الكود.

## دعم
إذا واجهت أي مشاكل، يرجى فتح تذكرة في مستودع GitHub.

## حل مشكلة سائق Google Chrome
إذا واجهت خطأ متعلق بـ `ChromeDriver`، يمكنك محاولة حل المشكلة باتباع الخطوات التالية:

1. **تحديث ChromeDriver**:
    - تأكد من أن إصدار ChromeDriver يتطابق مع إصدار Google Chrome المثبت على جهازك.
    - قم بتنزيل أحدث إصدار من ChromeDriver من [الرابط الرسمي](https://sites.google.com/chromium.org/driver/downloads) واستبدل الإصدار الحالي في مسار مشروعك.

2. **ضبط مسار ChromeDriver**:
    - إذا لم يتم العثور على `ChromeDriver` تلقائيًا، يمكنك تحديد المسار الكامل لـ `ChromeDriver` في الكود الخاص بك:
    ```javascript
    const puppeteer = require('puppeteer-extra');
    const chromePath = '/path/to/chromedriver'; // استبدل هذا بالمسار الفعلي لـ ChromeDriver
    puppeteer.launch({ executablePath: chromePath });
    ```

3. **منح الأذونات اللازمة (Linux فقط)**:
    - تأكد من أن `ChromeDriver` لديه أذونات التنفيذ:
    ```bash
    sudo chmod +x /path/to/chromedriver
    ```

باتباع هذه الخطوات، يجب أن تكون قادرًا على حل أي مشكلات تتعلق بـ `ChromeDriver` وتشغيل المشروع بنجاح.
