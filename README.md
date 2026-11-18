# STEINEX TRANSIT FX  (VST3 / Windows 64-bit)

## الحصول على الإضافة (بدون برامج على جهازك)
1. سجّل في github.com (مجاني) وسوّ مستودع جديد باسم `steinex-transit-fx`.
2. ارفع محتويات هذا المجلد كلها للمستودع (Add file > Upload files)، تأكد إن مجلد `.github` انرفع.
3. افتح تبويب **Actions** وانتظر البناء (حوالي 10 إلى 15 دقيقة). لو ما بدأ، اضغط Run workflow.
4. افتح التشغيلة الخضراء ونزّل **STEINEX-TRANSIT-FX-VST3-win64** من قسم Artifacts، وفك الضغط.
5. انسخ المجلد `STEINEX TRANSIT FX.vst3` إلى:
   `C:\Program Files\Common Files\VST3`
6. في FL Studio: Options > Manage plugins > **Find more plugins** (أو Verify plugins)، بعدها ابحث عن **TRANSIT FX** وحطه على قناة صوت (Mixer insert أو Channel).

## الاستخدام
- اضغط زر الطاقة (Power) في المودول عشان يشتغل. في FL Studio تقدر تعمل Automation للزر عشان ينطلق على الإيقاع.
- **ONE CLICK TRANSITIONS**: ضغطة تحمّل التركيبة وتشغّلها، وضغطة ثانية تطفيها.
- **المسجّل**: REC ثم شغّل صوتك ثم STOP. الإضافة تكمل التقاط ذيل الريفيرب والديلاي تلقائياً.
- اسحب الموجة (Waveform) إلى الـPlaylist في FL Studio. الملفات تنحفظ في:
  `Documents\STEINEX\TRANSIT FX\Recordings\STEINEX_TRANSITFX_001.wav` وما بعدها، ولا تنحذف تلقائياً.
- بريستاتك الخاصة تنحفظ في `Documents\STEINEX\TRANSIT FX\Presets`.

## البناء من الكود على جهازك
Visual Studio 2022 + CMake:
    cmake -B build -G "Visual Studio 17 2022" -A x64
    cmake --build build --config Release --target TransitFX_VST3

## الاختبار الذاتي (لينكس/ماك)
    cmake -B build-test -DSTEINEX_BUILD_TESTS=ON && cmake --build build-test --target TransitFXTest
