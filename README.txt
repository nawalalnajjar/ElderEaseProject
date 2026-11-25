=======================================================
 ElderEase - ASP.NET Core 8 Web API - تعليمات التشغيل
=======================================================

--- خطوات التشغيل لأول مرة ---

1. افتح الـ Solution: ElderEaseProject.sln  في Visual Studio 2022

2. تأكد من اتصال SQL Server (LocalDB):
   الاتصال الافتراضي: Server=(localdb)\mssqllocaldb;Database=ElderEaseDb

3. في Package Manager Console نفّذي:
   Update-Database

4. شغّلي المشروع (F5) ← يفتح Swagger تلقائياً

5. لفتح الموقع: انتقلي لـ http://localhost:5138/index.html

=======================================================
 بيانات تسجيل الدخول للأدمن
=======================================================

الرابط:       http://localhost:5138/login.html
المستخدم:     admin
كلمة المرور:  Admin@123

لتغيير كلمة المرور: عدّلي ملف appsettings.json في قسم "Admin"

=======================================================
 نقاط الـ API المتاحة (Endpoints)
=======================================================

GET/POST   /api/HelpRequests        - طلبات المساعدة
GET/POST   /api/Appointments        - المواعيد (يحتاج auth)
GET/POST   /api/Volunteers          - المتطوعون
GET/POST   /api/ContactMessages     - رسائل التواصل
GET/POST   /api/Organizations       - المؤسسات
POST       /api/Auth/login          - تسجيل الدخول
GET        /api/Admin/stats         - إحصائيات الداشبورد (Admin فقط)

=======================================================
 ما تم تعديله
=======================================================

Controllers/:
  ✓ AuthController.cs   - أُضيف التحقق من كلمة المرور + Role Claim
  ✓ AdminController.cs  - جديد: endpoint للإحصائيات

Models/:
  ✓ HelpRequest.cs - UserId أصبح nullable (int?)

Migrations/:
  ✓ UpdateModelsForWeek2 - migration لجعل HelpRequest.UserId nullable
  ✓ ApplicationDbContextModelSnapshot - محدَّث

wwwroot/assets/js/:
  ✓ admin.js         - ربط حقيقي مع API + JWT + تسجيل خروج
  ✓ appointments.js  - ربط حقيقي مع API + JWT
  ✓ contact.js       - ربط حقيقي مع /api/ContactMessages
  ✓ volunteers.js    - أسماء حقول صحيحة من قاعدة البيانات
  ✓ organizations.js - جلب من /api/Organizations

wwwroot/:
  ✓ login.html - صفحة تسجيل دخول جديدة (Admin)

Program.cs:
  ✓ CORS مضاف
  ✓ إعادة توجيه "/" لـ index.html

appsettings.json:
  ✓ قسم Admin: {Username, Password}

=======================================================
