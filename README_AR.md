# خادم Salem AI Agent (Claude)

هذه الحزمة مخصصة للنشر كخدمة Node.js مستقلة على Render، بينما يظل الموقع على GitHub Pages.

## إعداد Render
- ارفع هذا المجلد باسم `backend` إلى جذر مستودع GitHub.
- في Render أنشئ Web Service واربطه بالمستودع والفرع `SalemVisual`.
- Root Directory: `backend`
- Runtime: Node
- Build Command: `npm install`
- Start Command: `npm start`
- أضف Environment Variable باسم `ANTHROPIC_API_KEY` وقيمته مفتاحك من Anthropic Console.
- أضف `CLAUDE_MODEL` بقيمة نموذج متاح لحساب Anthropic لديك (يمكن ترك القيمة الافتراضية إن كانت مدعومة).
- بعد النشر اختبر رابط `https://YOUR-SERVICE.onrender.com/health` ويجب أن يظهر `{"status":"ok"}`.

## ربط واجهة الموقع
بعد ظهور رابط Render النهائي، يجب تعديل استدعاء الواجهة في `index.html` من المسار النسبي `/api/chat` إلى:
`https://YOUR-SERVICE.onrender.com/api/chat`
مع استبدال YOUR-SERVICE باسم خدمتك الحقيقي. لا تضع مفتاح API في HTML.

## الأمان
- لا ترفع ملف `.env` أو مفتاح API إلى GitHub.
- المفتاح يضاف في Render من Environment، وليس في ملفات الموقع.
- CORS مضبوط للسماح بأصل GitHub Pages الظاهر في إعداد الموقع الحالي فقط.
