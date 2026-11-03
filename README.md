# الحسينية — إدارة المشروع

واجهة عربية لإدارة المصروفات والتمويل والمقاولين. مصدر البيانات Google Sheets خاص يملكه صاحب المشروع؛ لا تُرفع البيانات المالية أو ملفات Excel أو نسخة المعاينة المحتوية على البيانات إلى المستودع العام.

## الحالة

- تم إنشاء جدول النظام في حساب مالك البيانات.
- يتضمن العمليات والإيداعات والمقاولين والمطابقة.
- النشر وتسجيل الدخول قيد الإعداد. نسخة المعاينة لم تُنشر هنا.

## إعداد Google

1. افتح Google Cloud Console بحساب صاحب البيانات وأنشئ مشروعًا باسم Husainiya Project Manager.
2. فعّل Google Sheets API.
3. اضبط Google Auth Platform / شاشة موافقة OAuth. اختر External إذا كان حساب Gmail شخصيًا، وأضف حساب المالك كمستخدم اختبار.
4. أنشئ OAuth Client من نوع Web application.
5. أضف Authorized JavaScript origin: https://coolmanx88.github.io (دون مسار المستودع).
6. احتفظ بـ Client ID لإعداد الواجهة. لا تستخدم Client Secret في المتصفح ولا ترفعه للمستودع.
7. واجهة الإنتاج تسترجع البيانات بعد موافقة Google فقط. Google Sheets هو من يفرض صلاحيات قراءة وكتابة الملف.

## النشر لاحقًا

Settings → Pages → Deploy from a branch → main / root.
يجب إكمال الواجهة وإعداد Client ID قبل اعتماد الموقع للاستخدام.

## قواعد الحساب

تُحتسب كل عملية مرة واحدة. الإيداعات منفصلة عن المصروفات. عقود الكميات غير المكتملة لا تعرض متبقيًا نهائيًا. سجل السيارة يبقى ضمن الصرف بطلب المالك مع تصنيف مستقل.

## المراجع

- https://developers.google.com/identity/oauth2/web/guides/use-token-model
- https://developers.google.com/workspace/sheets/api
