# Leon Template

صفحة ويب تعريفية (Landing Page) مبنية بلغتي **HTML5** و **CSS3**، وهي تطبيق عملي لما تم شرحه في المحاضرة.

## هيكل المشروع

leon/
├── index.html        (الصفحة الرئيسية)
├── css/
│   ├── main.css      (التنسيقات الخاصة بالصفحة)
│   └── all.min.css   (مكتبة Font Awesome للأيقونات)
├── images/           (الشعار والصور)
└── webfonts/         (خطوط الأيقونات)

## أقسام الصفحة (HTML)

1. **Header:** يحتوي على شعار الموقع (`logo.png`) وأيقونة قائمة، وعند تمرير الماوس عليها تظهر قائمة روابط (features, services, portfolio, about).
2. **Landing:** القسم الرئيسي بصورة خلفية، وفي منتصفه عنوان "Hello There" وفقرة ترحيبية.
3. **Features:** ثلاث ميزات، لكل منها أيقونة وعنوان ونص.
4. **Services:** أربع خدمات (graphic design, UI/UX, web design, web development) مع أيقونة لكل خدمة، وصورة جانبية.
5. **Portfolio:** ثلاثة مشاريع، لكل مشروع صورة وعنوان ووصف.
6. **About:** قسم تعريفي بصورة ونصين يفصل بينهما خط أفقي `<hr>`.
7. **Contact:** عنوان بريد إلكتروني وأيقونات التواصل الاجتماعي (Google, Facebook, Twitter).

الروابط في القائمة تستخدم المعرّفات (`#features`, `#services`...) للانتقال إلى كل قسم داخل الصفحة.

## شرح التنسيقات (CSS)

### 1. المتغيرات (Variables)
تم تعريف ألوان الموقع في `:root` لإعادة استخدامها بسهولة:
- `--main-color`: اللون الرئيسي (#10cab7).
- `--secondary-color`: اللون الثانوي (#2c4755).
- `--section-background`: لون خلفية الأقسام (#f6f6f6).

### 2. التنسيقات العامة (Global Style)
- `scroll-behavior: smooth`: انتقال سلس عند الضغط على روابط القائمة.
- `box-sizing: border-box` لكل العناصر: ليدخل الـ padding والـ border ضمن عرض العنصر.
- الخط الأساسي للصفحة هو **Work Sans**، وتم إلغاء هامش الـ body.
- الكلاس `.container`: حاوية لتنظيم محتوى الأقسام بمسافات داخلية.

### 3. الهيدر (Header)
- `display: flex` مع `justify-content: space-between` لوضع الشعار يسار والأيقونة يمين.
- `align-items: center` لمحاذاة العناصر عمودياً.
- القائمة المنسدلة:
  - `list-style: none` لإزالة النقاط.
  - `position: absolute` مع `right: 0` لتطفو تحت الأيقونة دون دفع المحتوى.
  - `display: none` لإخفائها، وتظهر بـ `display: block` عند `:hover` على `.links`.
  - `z-index: 1` لتظهر فوق باقي العناصر.
- الروابط: `display: block` لتأخذ كامل العرض، و`text-decoration: none` لإزالة التسطير.
- تأثير `:hover` على الروابط: يزداد `padding-left` مع `transition: 0.3s` لحركة ناعمة.
- فاصل رمادي بين الروابط باستخدام `:not(:last-child)` و`border-bottom`.

### 4. قسم Landing
- صورة الخلفية بـ `background-image` مع `background-size: cover` لتغطي القسم كاملاً.
- الارتفاع `calc(100vh - 60px)` أي ارتفاع الشاشة ناقص ارتفاع الهيدر.
- توسيط المحتوى بالمنتصف: `position: absolute` مع `left: 50%` و`top: 50%` و`transform: translate(-50%, -50%)`.
- العنوان بحجم 50px وبلون `--main-color`، والفقرة بحجم 20px و`line-height: 2` لتباعد الأسطر.

## التقنيات المستخدمة
- HTML5
- CSS3 (Flexbox, Variables, Positioning, Transitions)
- Font Awesome (الأيقونات)
- Google Fonts (Work Sans, Oswald)


