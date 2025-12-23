
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أداة إعداد التقارير التعليمية (نموذج تجريبي)</title>
<style>
body {
  font-family: 'Segoe UI', Tahoma, Arial, sans-serif;
  background: linear-gradient(135deg, #eef7f5 0%, #e0f2f1 100%);
  margin: 0;
  padding: 20px;
  font-size: 13px;
  color: #0a3b40;
}
.tool {
  max-width: 900px;
  margin: auto;
  background: white;
  padding: 25px;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(10, 59, 64, 0.12);
  border: 1px solid rgba(10, 59, 64, 0.08);
}
.tool h2 {
  text-align: center;
  color: #0a3b40;
  margin-bottom: 20px;
  font-size: 22px;
  padding-bottom: 12px;
  border-bottom: 2px solid #e0f2f1;
  position: relative;
}
.tool h2:after {
  content: '';
  position: absolute;
  bottom: -2px;
  right: 45%;
  width: 10%;
  height: 2px;
  background: #0a3b40;
}
label {
  font-weight: 700;
  margin-top: 16px;
  display: block;
  color: #0a3b40;
  font-size: 12px;
}
.input-hint {
  font-size: 10px;
  color: #689f38;
  margin-top: 2px;
  margin-bottom: 6px;
  font-weight: normal;
  background: #f1f8e9;
  padding: 4px 8px;
  border-radius: 4px;
  border-right: 3px solid #689f38;
}
input, textarea, select {
  width: 100%;
  padding: 10px;
  margin-top: 4px;
  border-radius: 8px;
  border: 1px solid #b0bec5;
  font-size: 13px;
  box-sizing: border-box;
  transition: all 0.3s ease;
  background: #fafafa;
}
input:focus, textarea:focus, select:focus {
  outline: none;
  border-color: #0a3b40;
  box-shadow: 0 0 0 2px rgba(10, 59, 64, 0.1);
  background: white;
}
textarea {
  resize: vertical;
  min-height: 80px;
  max-height: 140px;
  overflow-y: auto;
  line-height: 1.5;
}
.small-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 8px;
  margin: 15px 0;
  background: #f8f9fa;
  padding: 12px;
  border-radius: 8px;
  border: 1px solid #e0e0e0;
}
.small-grid input,
.small-grid select {
  font-size: 11px;
  padding: 8px 6px;
  height: 36px;
}
.auto-row {
  display: flex;
  gap: 8px;
  margin-top: 10px;
  margin-bottom: 8px;
}
.auto-btn {
  flex: 1;
  background: #e0f2f1;
  border: 1px solid #0a3b40;
  color: #0a3b40;
  font-size: 12px;
  padding: 10px;
  border-radius: 6px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 600;
}
.auto-btn:hover {
  background: #0a3b40;
  color: white;
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(10, 59, 64, 0.2);
}
.clear-btn {
  background: #fdecea;
  border: 1px solid #c62828;
  color: #c62828;
}
.clear-btn:hover {
  background: #c62828;
  color: white;
}
button#printBtn {
  margin-top: 25px;
  padding: 14px;
  width: 100%;
  background: linear-gradient(135deg, #0a3b40 0%, #0d4a50 100%);
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 16px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: bold;
  letter-spacing: 1px;
}
button#printBtn:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 15px rgba(10, 59, 64, 0.3);
}
.report {
  display: none;
}
@media print {
  body { background: white; padding: 0; }
  .tool { display: none; }
  .report { display: block; max-width: 210mm; margin: 0 auto; }
}
.header {
  background: linear-gradient(135deg, #0a3b40 0%, #0d4a50 100%);
  color: white;
  text-align: center;
  padding: 10px;
  margin-bottom: 12px;
  border-radius: 6px;
  min-height: auto;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}
.header-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
}
.ministry-title {
  font-size: 16pt;
  font-weight: bold;
}
.ministry-subtitle {
  font-size: 10pt;
  opacity: 0.9;
}
.school-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 3px;
  margin-top: 4px;
}
.edu-info {
  font-weight: bold;
  font-size: 11pt;
}
.school-name {
  font-weight: bold;
  font-size: 11pt;
  color: #e0f7fa;
}
.hijri-date {
  font-size: 10pt;
  margin-top: 4px;
  color: #e0f7fa;
  opacity: 0.9;
}
.top-info.two-lines {
  display: flex;
  flex-direction: column;
  gap: 6px;
  margin-bottom: 12px;
}
.top-row {
  display: grid;
  gap: 4px;
}
.top-row.first {
  grid-template-columns: repeat(3, 1fr);
}
.top-row.second {
  grid-template-columns: repeat(4, 1fr);
}
.box {
  border: 1px solid #0a3b40;
  padding: 4px;
  text-align: center;
  font-size: 7pt;
  min-height: 26px;
  max-height: 50px;
  border-radius: 4px;
  background: #f8f9fa;
  overflow: hidden;
  text-overflow: ellipsis;
}
.box strong {
  display: block;
  font-size: 7pt;
  color: #0a3b40;
  margin-bottom: 2px;
}
.box div {
  font-size: 7pt;
  line-height: 1.3;
  max-height: 32px;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
.goal-section {
  background: #e8f5e9;
  border-right: 3px solid #2e7d32;
  border-radius: 8px;
  padding: 10px;
  margin-bottom: 12px;
  text-align: center;
  min-height: auto;
  max-height: 100px;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(46, 125, 50, 0.1);
}
.goal-section strong {
  font-size: 12px;
  margin-bottom: 4px;
  color: #1b5e20;
}
.goal-section div {
  font-size: 11px;
  line-height: 1.4;
  max-height: 70px;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
}
.grid2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 12px;
}
.grid4 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
  margin-bottom: 12px;
}
.section {
  border: 1px solid #0a3b40;
  padding: 8px;
  border-radius: 8px;
  font-size: 11px;
  max-height: 120px;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(10, 59, 64, 0.05);
}
.section strong {
  font-size: 11px;
  margin-bottom: 4px;
  display: block;
  color: #0a3b40;
}
.section div {
  font-size: 11px;
  line-height: 1.4;
  max-height: 90px;
  overflow-y: auto;
  padding-right: 5px;
}
.section.motivators {
  border: 1px solid #9ccc65;
  background: #f1f8e9;
  min-height: 60px;
  max-height: 100px;
  height: auto;
  padding: 6px;
  font-size: 10px;
}
.section.motivators strong {
  font-size: 11px;
  margin-bottom: 2px;
  color: #689f38;
}
.section.motivators div {
  font-size: 10px;
  line-height: 1.3;
  max-height: 70px;
}
.section.strengths {
  border: 1px solid #0d47a1;
  background: #e3f2fd;
  min-height: 60px;
  max-height: 100px;
  height: auto;
  padding: 6px;
  font-size: 10px;
}
.section.strengths strong {
  font-size: 11px;
  margin-bottom: 2px;
  color: #0d47a1;
}
.section.strengths div {
  font-size: 10px;
  line-height: 1.3;
  max-height: 70px;
}
.section.challenges {
  border: 1px solid #f57f17;
  background: #fffde7;
  min-height: 60px;
  max-height: 100px;
  height: auto;
  padding: 6px;
  font-size: 10px;
}
.section.challenges strong {
  font-size: 11px;
  margin-bottom: 2px;
  color: #f57f17;
}
.section.challenges div {
  font-size: 10px;
  line-height: 1.3;
  max-height: 70px;
}
.section.weaknesses {
  border: 1px solid #c62828;
  background: #ffebee;
  min-height: 60px;
  max-height: 100px;
  height: auto;
  padding: 6px;
  font-size: 10px;
}
.section.weaknesses strong {
  font-size: 11px;
  margin-bottom: 2px;
  color: #c62828;
}
.section.weaknesses div {
  font-size: 10px;
  line-height: 1.3;
  max-height: 70px;
}
.images {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  margin: 20px 0;
}
.images img {
  width: 100%;
  max-height: 200px;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}
.signatures {
  margin-top: 20px;
  padding-top: 12px;
  border-top: 2px solid #ccc;
  display: flex;
  justify-content: space-between;
  font-size: 10pt;
}
.teacher-signature, .principal-signature {
  text-align: center;
  width: 45%;
}
.teacher-signature input, .principal-signature input {
  width: 80%;
  font-size: 10pt;
  padding: 6px;
  margin-top: 6px;
  border: none;
  border-bottom: 2px solid #ccc;
  text-align: center;
  background: transparent;
}
.signature-label {
  font-weight: bold;
  color: #0a3b40;
  margin-bottom: 6px;
  font-size: 11px;
}
.instructions {
  background: #e3f2fd;
  border-radius: 8px;
  padding: 12px;
  margin: 15px 0;
  border-right: 4px solid #0d47a1;
  font-size: 12px;
  line-height: 1.5;
}
.instructions strong {
  color: #0d47a1;
  display: block;
  margin-bottom: 5px;
}
</style>
</head>
<body>

<div class="tool">
<h2>أداة إعداد التقارير التعليمية (نموذج تجريبي)</h2>

<div class="instructions">
<strong>تعليمات الاستخدام:</strong>
املأ الحقول أدناه، استخدم الأزرار العلوية لملء النماذج الجاهزة، ثم اضغط على زر "معاينة وطباعة التقرير" للحصول على التقرير النهائي.
</div>

<label>إدارة التعليم</label>
<div class="input-hint">اختر إدارة التعليم التابعة لها المدرسة</div>
<select id="eduSelect" onchange="updateEduInfo(this.value)">
  <option value="">اختر إدارة التعليم</option>
  <option value="الإدارة العامة للتعليم بمنطقة الرياض" selected>الإدارة العامة للتعليم بمنطقة الرياض</option>
  <option value="الإدارة العامة للتعليم بمنطقة مكة المكرمة">الإدارة العامة للتعليم بمنطقة مكة المكرمة</option>
  <option value="الإدارة العامة للتعليم بمنطقة المدينة المنورة">الإدارة العامة للتعليم بمنطقة المدينة المنورة</option>
  <option value="الإدارة العامة للتعليم بالمنطقة الشرقية">الإدارة العامة للتعليم بالمنطقة الشرقية</option>
  <option value="الإدارة العامة للتعليم بمنطقة القصيم">الإدارة العامة للتعليم بمنطقة القصيم</option>
  <option value="الإدارة العامة للتعليم بمنطقة عسير">الإدارة العامة للتعليم بمنطقة عسير</option>
  <option value="الإدارة العامة للتعليم بمنطقة تبوك">الإدارة العامة للتعليم بمنطقة تبوك</option>
  <option value="الإدارة العامة للتعليم بمنطقة حائل">الإدارة العامة للتعليم بمنطقة حائل</option>
  <option value="الإدارة العامة للتعليم بمنطقة الحدود الشمالية">الإدارة العامة للتعليم بمنطقة الحدود الشمالية</option>
  <option value="الإدارة العامة للتعليم بمنطقة جازان">الإدارة العامة للتعليم بمنطقة جازان</option>
  <option value="الإدارة العامة للتعليم بمنطقة نجران">الإدارة العامة للتعليم بمنطقة نجران</option>
  <option value="الإدارة العامة للتعليم بمنطقة الباحة">الإدارة العامة للتعليم بمنطقة الباحة</option>
  <option value="الإدارة العامة للتعليم بمنطقة الجوف">الإدارة العامة للتعليم بمنطقة الجوف</option>
  <option value="الإدارة العامة للتعليم بمحافظة الأحساء">الإدارة العامة للتعليم بمحافظة الأحساء</option>
  <option value="الإدارة العامة للتعليم بمحافظة الطائف">الإدارة العامة للتعليم بمحافظة الطائف</option>
  <option value="الإدارة العامة للتعليم بمحافظة جدة">الإدارة العامة للتعليم بمحافظة جدة</option>
</select>

<label>اسم المدرسة</label>
<div class="input-hint">أدخل الاسم الكامل للمدرسة مثل: مدرسة الملك عبدالله الثانوية</div>
<input id="schoolInput" placeholder="أدخل اسم المدرسة هنا" oninput="sync('school',this.value)">

<div class="small-grid">
  <select onchange="sync('reportTitle',this.value)" id="reportSelect">
    <option value="">اختر نوع التقرير</option>
    <option value="تقرير نشاط إثرائي" selected>تقرير نشاط إثرائي</option>
    <option value="تقرير خطة علاجية">تقرير خطة علاجية</option>
  </select>
  <input placeholder="المستهدفون" oninput="sync('target',this.value)" maxlength="30" title="الحد الأقصى 30 حرف">
  <div class="input-hint">مثال: الطلاب المتميزين</div>
  
  <input placeholder="العدد" oninput="sync('count',this.value)" maxlength="10" title="الحد الأقصى 10 أرقام">
  <div class="input-hint">مثال: 25 طالباً</div>
  
  <input placeholder="مكان التنفيذ" oninput="sync('location',this.value)" maxlength="40" title="الحد الأقصى 40 حرف">
  <div class="input-hint">مثال: المختبر العلمي</div>
  
  <select id="semesterSelect" onchange="sync('semester',this.value)">
    <option value="">اختر الفصل الدراسي</option>
    <option value="الفصل الدراسي الأول">الفصل الدراسي الأول</option>
    <option value="الفصل الدراسي الثاني">الفصل الدراسي الثاني</option>
  </select>
  
  <input placeholder="الصف" oninput="sync('grade',this.value)" maxlength="20" title="الحد الأقصى 20 حرف">
  <div class="input-hint">مثال: الثالث الثانوي</div>
  
  <input placeholder="المادة" oninput="sync('subject',this.value)" maxlength="25" title="الحد الأقصى 25 حرف">
  <div class="input-hint">مثال: الرياضيات</div>
</div>

<!-- اختيار النص التلقائي -->
<div class="auto-row">
  <button class="auto-btn" onclick="loadSmartText(1)">النص الإثرائي 1</button>
  <button class="auto-btn" onclick="loadSmartText(2)">النص الإثرائي 2</button>
  <button class="auto-btn" onclick="loadSmartText(3)">النص الإثرائي 3</button>
  <button class="auto-btn clear-btn" onclick="clearAllFields()">مسح الحقول</button>
</div>
<div class="auto-row">
  <button class="auto-btn" onclick="loadSmartText(4)">النص العلاجي 1</button>
  <button class="auto-btn" onclick="loadSmartText(5)">النص العلاجي 2</button>
</div>

<label>الهدف التربوي (الحد الأقصى: 150 حرف)</label>
<div class="input-hint">مثال: تنمية مهارات التفكير النقدي والإبداعي لدى الطلاب المتميزين</div>
<textarea id="goalInput" oninput="sync('goal',this.value)" maxlength="150" title="الحد الأقصى 150 حرف"></textarea>

<label>وصف مختصر (الحد الأقصى: 200 حرف)</label>
<div class="input-hint">مثال: برنامج إثرائي متخصص لصقل مهارات التفكير العليا والبحث العلمي</div>
<textarea id="desc1Input" oninput="sync('desc1',this.value)" maxlength="200" title="الحد الأقصى 200 حرف"></textarea>

<label>إجراءات التنفيذ (الحد الأقصى: 300 حرف)</label>
<div class="input-hint">مثال: اختيار الطلاب الموهوبين، ورش عمل متخصصة، مشاريع بحثية، منافسات علمية</div>
<textarea id="desc2Input" oninput="sync('desc2',this.value)" maxlength="300" title="الحد الأقصى 300 حرف"></textarea>

<label>النتائج (الحد الأقصى: 250 حرف)</label>
<div class="input-hint">مثال: تطوير 12 مشروعاً بحثياً، تحسن مهارات التحليل بنسبة 45%، فوز في مسابقات محلية</div>
<textarea id="desc3Input" oninput="sync('desc3',this.value)" maxlength="250" title="الحد الأقصى 250 حرف"></textarea>

<label>التوصيات (الحد الأقصى: 250 حرف)</label>
<div class="input-hint">مثال: توسيع نطاق البرنامج، تدريب معلمين متخصصين، إنشاء مكتبة مصادر</div>
<textarea id="desc4Input" oninput="sync('desc4',this.value)" maxlength="250" title="الحد الأقصى 250 حرف"></textarea>

<!-- الصف الأول: المحفزات ونقاط القوة -->
<div class="grid2">
  <div>
    <label>المحفزات (الحد الأقصى: 200 حرف)</label>
    <div class="input-hint">مثال: جوائز مالية رمزية، رحلات تعليمية، نشر الأبحاث، شهادات تميز</div>
    <textarea id="motivatorsInput" oninput="sync('motivators',this.value)" maxlength="200" title="الحد الأقصى 200 حرف"></textarea>
  </div>
  <div>
    <label>نقاط القوة (الحد الأقصى: 200 حرف)</label>
    <div class="input-hint">مثال: كوادر تدريسية متميزة، مختبرات مجهزة، منهجية علمية دقيقة</div>
    <textarea id="strengthsInput" oninput="sync('strengths',this.value)" maxlength="200" title="الحد الأقصى 200 حرف"></textarea>
  </div>
</div>

<!-- الصف الثاني: التحديات ومواطن القصور -->
<div class="grid2">
  <div>
    <label>التحديات (الحد الأقصى: 200 حرف)</label>
    <div class="input-hint">مثال: تحديد الموهوبين بدقة، تكاليف البرامج المتخصصة، ضيق الوقت الدراسي</div>
    <textarea id="challengesInput" oninput="sync('challenges',this.value)" maxlength="200" title="الحد الأقصى 200 حرف"></textarea>
  </div>
  <div>
    <label>مواطن القصور (الحد الأقصى: 200 حرف)</label>
    <div class="input-hint">مثال: نقص الخبرات المتقدمة، محدودية التمويل، صعوبة القياس الكمي</div>
    <textarea id="weaknessesInput" oninput="sync('weaknesses',this.value)" maxlength="200" title="الحد الأقصى 200 حرف"></textarea>
  </div>
</div>

<label>إرفاق الصور (اختياري - الحد الأقصى: صورتين)</label>
<div class="input-hint">يمكن إرفاق صورتين كحد أقصى تظهران فعاليات النشاط</div>
<input type="file" multiple accept="image/*" onchange="loadImages(this)" title="يمكن إرفاق صورتين كحد أقصى">

<div class="signatures">
  <div class="teacher-signature">
    <div class="signature-label">اسم المعلم</div>
    <div class="input-hint">مثال: أحمد محمد علي</div>
    <input type="text" id="teacherInput" placeholder="أدخل اسم المعلم" oninput="sync('teacherName', this.value)" maxlength="50">
  </div>
  <div class="principal-signature">
    <div class="signature-label">اسم مدير المدرسة</div>
    <div class="input-hint">مثال: خالد بن عبدالله السليم</div>
    <input type="text" id="principalInput" placeholder="أدخل اسم المدير" oninput="sync('principalName', this.value)" maxlength="50">
  </div>
</div>

<button id="printBtn" onclick="window.print()">معاينة وطباعة التقرير</button>
</div>

<!-- قسم التقرير للطباعة -->
<div class="report">
<div class="header">
  <div class="header-content">
    <div class="ministry-title">وزارة التعليم</div>
    <div class="ministry-subtitle">Ministry of Education</div>
    <div class="school-info">
      <div class="edu-info" id="eduHeader">الإدارة العامة للتعليم بمنطقة الرياض</div>
      <div class="school-name" id="school"></div>
    </div>
    <div class="hijri-date" id="hijriDate">جاري تحميل التاريخ الهجري...</div>
  </div>
</div>

<div class="top-info two-lines">
  <div class="top-row first">
    <div class="box"><strong>الفصل الدراسي</strong><div id="semester"></div></div>
    <div class="box"><strong>الصف</strong><div id="grade"></div></div>
    <div class="box"><strong>المادة</strong><div id="subject"></div></div>
  </div>
  <div class="top-row second">
    <div class="box"><strong>التقرير</strong><div id="reportTitle"></div></div>
    <div class="box"><strong>المستهدفون</strong><div id="target"></div></div>
    <div class="box"><strong>العدد</strong><div id="count"></div></div>
    <div class="box"><strong>مكان التنفيذ</strong><div id="location"></div></div>
  </div>
</div>

<div class="goal-section">
<strong>الهدف التربوي</strong>
<div id="goal"></div>
</div>

<div class="grid2">
  <div class="section"><strong>وصف مختصر</strong><div id="desc1"></div></div>
  <div class="section"><strong>إجراءات التنفيذ</strong><div id="desc2"></div></div>
</div>

<div class="grid2">
  <div class="section"><strong>النتائج</strong><div id="desc3"></div></div>
  <div class="section"><strong>التوصيات</strong><div id="desc4"></div></div>
</div>

<!-- الصف الأول في التقرير: المحفزات ونقاط القوة -->
<div class="grid4">
  <div class="section motivators"><strong>المحفزات</strong><div id="motivators"></div></div>
  <div class="section strengths"><strong>نقاط القوة</strong><div id="strengths"></div></div>
</div>

<!-- الصف الثاني في التقرير: التحديات ومواطن القصور -->
<div class="grid4">
  <div class="section challenges"><strong>التحديات</strong><div id="challenges"></div></div>
  <div class="section weaknesses"><strong>مواطن القصور</strong><div id="weaknesses"></div></div>
</div>

<div class="images" id="imagesBox"></div>

<div class="signatures">
  <div class="teacher-signature">
    <div class="signature-label">المعلم</div>
    <div id="teacherName"></div>
  </div>
  <div class="principal-signature">
    <div class="signature-label">مدير المدرسة</div>
    <div id="principalName"></div>
  </div>
</div>
</div>

<script>
// قاعدة البيانات للنصوص الذكية والمتنوعة (5 نصوص مختلفة)
const smartTextsDatabase = {
  // النصوص الإثرائية (1-3)
  1: {
    reportType: "تقرير نشاط إثرائي",
    goal: "تنمية التفكير النقدي والإبداعي لدى الطلاب المتميزين عبر أنشطة متقدمة",
    desc1: "برنامج إثرائي متخصص لصقل مهارات التفكير العليا والبحث العلمي",
    desc2: "اختيار الطلاب الموهوبين، ورش عمل متخصصة، مشاريع بحثية، منافسات علمية، متابعة فردية",
    desc3: "تطوير 12 مشروعاً بحثياً مبتكراً، تحسن مهارات التحليل بنسبة 45%، فوز في مسابقات محلية",
    desc4: "توسيع نطاق البرنامج، تدريب معلمين متخصصين، إنشاء مكتبة مصادر، توثيق التجارب الناجحة",
    motivators: "جوائز مالية رمزية، رحلات تعليمية، نشر الأبحاث، شهادات تميز معتمدة",
    strengths: "كوادر تدريسية متميزة، مختبرات مجهزة، منهجية علمية دقيقة، دعم إداري مستمر",
    challenges: "تحديد الموهوبين بدقة، تكاليف البرامج المتخصصة، ضيق الوقت الدراسي",
    weaknesses: "نقص الخبرات المتقدمة، محدودية التمويل، صعوبة القياس الكمي"
  },
  2: {
    reportType: "تقرير نشاط إثرائي",
    goal: "تعزيز المهارات البحثية والعلمية لدى النخبة الطلابية الواعدة",
    desc1: "مشروع علمي متكامل لتنمية القدرات البحثية والابتكارية",
    desc2: "تقييم القدرات البحثية، تدريب على المنهج العلمي، إشراف أكاديمي، تقديم المشاريع، تقييم النتائج",
    desc3: "إنتاج 8 أبحاث علمية قابلة للنشر، تنمية مهارات العرض بنسبة 60%، اكتشاف مواهب بحثية",
    desc4: "إنشاء نادي البحث العلمي، تدريب المدربين، توفير منح دراسية، إقامة مؤتمر طلابي",
    motivators: "منح بحثية صغيرة، مشاركة في مؤتمرات، نشر في مجلات طلابية، زيارات لمؤسسات بحثية",
    strengths: "شراكات مع جامعات، مراكز بحثية داعمة، مكتبة رقمية شاملة، خبراء استشاريون",
    challenges: "صعوبة النشر العلمي، محدودية الإشراف المتخصص، تكاليف المعدات البحثية",
    weaknesses: "ضعف الخلفية البحثية، قلة الوقت للبحث، محدودية المراجع المتخصصة"
  },
  3: {
    reportType: "تقرير نشاط إثرائي",
    goal: "تطوير القدرات الابتكارية والتكنولوجية للطلاب الموهوبين",
    desc1: "برنامج تقني متقدم لتعزيز الابتكار والتفكير الحاسوبي",
    desc2: "تدريب على البرمجة، ورش الابتكار التقني، مشاريع تكنولوجية، مسابقات برمجية، معارض ابتكار",
    desc3: "تصميم 15 تطبيقاً تعليمياً، فوز في 3 مسابقات برمجية، إنشاء نادٍ تقني، اكتشاف مواهب تقنية",
    desc4: "تطوير منهج تقني متخصص، تأهيل مدربين تقنيين، توفير أجهزة متطورة، إنشاء حاضنة تقنية",
    motivators: "جوائز لأفضل التطبيقات، تدريبات في شركات تقنية، شهادات احترافية، رحلات تقنية",
    strengths: "معامل حاسب متطورة، مدربون متخصصون، شراكات مع شركات تقنية، بيئة محفزة للإبداع",
    challenges: "تحديث الأجهزة باستمرار، سرعة التطور التقني، نقص الكوادر المتخصصة",
    weaknesses: "فجوة المهارات التقنية، تكاليف الصيانة العالية، محدودية البرامج المتخصصة"
  },
  // النصوص العلاجية (4-5)
  4: {
    reportType: "تقرير خطة علاجية",
    goal: "معالجة الصعوبات القرائية والكتابية لدى الطلاب المتأخرين دراسياً",
    desc1: "برنامج تدخلي مكثف لتحسين المهارات الأساسية في القراءة والكتابة",
    desc2: "تشخيص فردي للصعوبات، جلسات علاجية مكثفة، استخدام وسائل مساعدة، متابعة أسرية، تقييم دوري",
    desc3: "تحسن مهارات القراءة بنسبة 70%، تحسن الكتابة بنسبة 65%، زيادة الثقة اللغوية، تفاعل إيجابي",
    desc4: "تطوير أدوات التشخيص، تدريب فرق علاجية، إنشاء بنك أنشطة، تعزيز الشراكة الأسرية",
    motivators: "برامج تحفيزية أسبوعية، شهادات تحسن، نشر قصص نجاح، جوائز للتقدم الملحوظ",
    strengths: "معلمون متخصصون في الصعوبات، وسائل تعليمية مساندة، دعم إداري كامل، منهجية علاجية مثبتة",
    challenges: "تفاوت مستويات الصعوبات، مقاومة بعض الطلاب، ضعف المتابعة الأسرية",
    weaknesses: "نقص الكوادر المتخصصة، محدودية الوقت العلاجي، صعوبة التشخيص الدقيق"
  },
  5: {
    reportType: "تقرير خطة علاجية",
    goal: "تحسين المهارات الحسابية والرياضية للطلاب الضعفاء دراسياً",
    desc1: "برنامج علاجي منهجي لمعالجة ضعف المهارات الرياضية الأساسية",
    desc2: "تقييم المهارات الحسابية، تدريبات علاجية مكثفة، استخدام وسائل بصرية، أنشطة تطبيقية، تقييم تقدم",
    desc3: "تحسن العمليات الحسابية بنسبة 75%، فهم المفاهيم الرياضية، زيادة الثقة بالنفس، تحسن المشاركة",
    desc4: "تطوير مواد علاجية، تدريب معلمي رياضيات، إنشاء مختبر رياضي، تعزيز التعلم التطبيقي",
    motivators: "مسابقات حسابية، شهادات تقدم، نشر الإنجازات، رحلات تعليمية",
    strengths: "وسائل تعليمية مبتكرة، معلمون متمرسون، بيئة تعلم محفزة، دعم نفسي مستمر",
    challenges: "صعوبة بعض المفاهيم، تفاوت القدرات الاستيعابية، محدودية الوقت",
    weaknesses: "نقص الوسائل التعليمية، ضعف الخلفية الرياضية، صعوبة الربط بالتطبيق"
  }
};

// تقصير النصوص الطويلة لعرضها في المربعات
function truncateText(text, maxLength) {
  if (!text) return '';
  if (text.length <= maxLength) return text;
  return text.substring(0, maxLength - 3) + '...';
}

// دالة للحصول على التاريخ الهجري من API خارجي
async function getHijriDate() {
  try {
    const response = await fetch('https://api.aladhan.com/v1/gToH');
    
    if (!response.ok) {
      throw new Error('فشل في الحصول على التاريخ الهجري');
    }
    
    const data = await response.json();
    
    if (data.code === 200 && data.data) {
      const hijri = data.data.hijri;
      const dateString = `${hijri.day} ${hijri.month.ar} ${hijri.year} هـ`;
      document.getElementById('hijriDate').textContent = `التاريخ الهجري: ${dateString}`;
    } else {
      document.getElementById('hijriDate').textContent = "التاريخ الهجري: غير متاح";
    }
  } catch (error) {
    console.error('خطأ في الحصول على التاريخ الهجري:', error);
    document.getElementById('hijriDate').textContent = "التاريخ الهجري: ١ رمضان ١٤٤٥ هـ";
  }
}

// دالة لتحديث معلومات إدارة التعليم في الهيدر
function updateEduInfo(value) {
  if (!value) return;
  const eduHeader = document.getElementById('eduHeader');
  if (eduHeader) {
    eduHeader.textContent = truncateText(value, 50);
  }
}

function sync(id, value) {
  const el = document.getElementById(id);
  if (el) {
    let maxLength;
    switch(id) {
      case 'goal': maxLength = 150; break;
      case 'desc1': maxLength = 200; break;
      case 'desc2': maxLength = 300; break;
      case 'desc3': maxLength = 250; break;
      case 'desc4': maxLength = 250; break;
      case 'motivators': maxLength = 200; break;
      case 'strengths': maxLength = 200; break;
      case 'challenges': maxLength = 200; break;
      case 'weaknesses': maxLength = 200; break;
      case 'target': maxLength = 30; break;
      case 'count': maxLength = 10; break;
      case 'location': maxLength = 40; break;
      case 'grade': maxLength = 20; break;
      case 'subject': maxLength = 25; break;
      default: maxLength = 100;
    }
    
    el.textContent = truncateText(value, maxLength);
  }
}

// دالة رئيسية لتحميل النص الذكي - تم إصلاحها
function loadSmartText(textNumber) {
  // الحصول على النص من قاعدة البيانات
  const textData = smartTextsDatabase[textNumber];
  if (!textData) {
    alert("النص غير متوفر، الرجاء المحاولة مرة أخرى");
    return;
  }
  
  // تحديث نوع التقرير في القائمة المنسدلة
  const reportSelect = document.getElementById('reportSelect');
  reportSelect.value = textData.reportType;
  sync('reportTitle', textData.reportType);
  
  // تعبئة الحقول مع النصوص
  document.getElementById('goalInput').value = textData.goal;
  document.getElementById('desc1Input').value = textData.desc1;
  document.getElementById('desc2Input').value = textData.desc2;
  document.getElementById('desc3Input').value = textData.desc3;
  document.getElementById('desc4Input').value = textData.desc4;
  document.getElementById('motivatorsInput').value = textData.motivators;
  document.getElementById('strengthsInput').value = textData.strengths;
  document.getElementById('challengesInput').value = textData.challenges;
  document.getElementById('weaknessesInput').value = textData.weaknesses;
  
  // مزامنة مع العرض
  sync('goal', textData.goal);
  sync('desc1', textData.desc1);
  sync('desc2', textData.desc2);
  sync('desc3', textData.desc3);
  sync('desc4', textData.desc4);
  sync('motivators', textData.motivators);
  sync('strengths', textData.strengths);
  sync('challenges', textData.challenges);
  sync('weaknesses', textData.weaknesses);
  
  // تعبئة تلقائية للحقول الأخرى بناءً على نوع التقرير
  if (textData.reportType === "تقرير نشاط إثرائي") {
    document.querySelector('input[placeholder="المستهدفون"]').value = "الطلاب المتميزين أكاديمياً";
    document.querySelector('input[placeholder="العدد"]').value = "18";
    document.querySelector('input[placeholder="مكان التنفيذ"]').value = "المختبر العلمي المتقدم";
    document.querySelector('input[placeholder="الصف"]').value = "الثالث الثانوي";
    document.querySelector('input[placeholder="المادة"]').value = "الفيزياء";
    
    sync('target', "الطلاب المتميزين أكاديمياً");
    sync('count', "18");
    sync('location', "المختبر العلمي المتقدم");
    sync('grade', "الثالث الثانوي");
    sync('subject', "الفيزياء");
  } else if (textData.reportType === "تقرير خطة علاجية") {
    document.querySelector('input[placeholder="المستهدفون"]').value = "الطلاب المتأخرين دراسياً";
    document.querySelector('input[placeholder="العدد"]').value = "12";
    document.querySelector('input[placeholder="مكان التنفيذ"]').value = "غرفة المصادر التعليمية";
    document.querySelector('input[placeholder="الصف"]').value = "الأول المتوسط";
    document.querySelector('input[placeholder="المادة"]').value = "الرياضيات";
    
    sync('target', "الطلاب المتأخرين دراسياً");
    sync('count', "12");
    sync('location', "غرفة المصادر التعليمية");
    sync('grade', "الأول المتوسط");
    sync('subject', "الرياضيات");
  }
  
  // تعبئة الفصل الدراسي
  document.getElementById('semesterSelect').value = "الفصل الدراسي الأول";
  sync('semester', "الفصل الدراسي الأول");
  
  // تعبئة أسماء المعلم والمدير
  document.getElementById('teacherInput').value = "أحمد محمد علي";
  document.getElementById('principalInput').value = "خالد بن عبدالله السليم";
  sync('teacherName', "أحمد محمد علي");
  sync('principalName', "خالد بن عبدالله السليم");
  
  // إشعار للمستخدم
  alert(`تم تحميل ${textData.reportType} - النص ${textNumber} بنجاح!`);
}

function clearAllFields() {
  const fieldsToClear = [
    'goalInput', 'desc1Input', 'desc2Input', 'desc3Input', 'desc4Input',
    'motivatorsInput', 'strengthsInput', 'challengesInput', 'weaknessesInput',
    'teacherInput', 'principalInput', 'schoolInput'
  ];
  
  const placeholders = [
    'المستهدفون',
    'العدد',
    'مكان التنفيذ',
    'الصف',
    'المادة'
  ];
  
  fieldsToClear.forEach(id => {
    const element = document.getElementById(id);
    if (element) {
      element.value = '';
      const syncId = id.replace('Input', '');
      if (!['teacher', 'principal', 'school'].includes(syncId)) {
        sync(syncId, '');
      }
    }
  });
  
  placeholders.forEach(placeholder => {
    const input = document.querySelector(`input[placeholder="${placeholder}"]`);
    if (input) input.value = '';
  });
  
  sync('target', '');
  sync('count', '');
  sync('location', '');
  sync('grade', '');
  sync('subject', '');
  sync('teacherName', '');
  sync('principalName', '');
  
  document.getElementById('semesterSelect').selectedIndex = 0;
  sync('semester', '');
  
  document.getElementById('imagesBox').innerHTML = '';
  
  // إعادة تعيين نوع التقرير
  document.getElementById('reportSelect').selectedIndex = 0;
  sync('reportTitle', '');
}

function loadImages(input) {
  const box = document.getElementById("imagesBox");
  box.innerHTML = "";
  const files = Array.from(input.files).slice(0, 2);
  if (files.length > 2) {
    alert("يمكنك إرفاق صورتين كحد أقصى");
  }
  files.forEach(file => {
    const reader = new FileReader();
    reader.onload = e => {
      const img = document.createElement("img");
      img.src = e.target.result;
      box.appendChild(img);
    };
    reader.readAsDataURL(file);
  });
}

// تعبئة أولية للمساعدة في التجربة
window.onload = async function() {
  document.getElementById('schoolInput').value = "مدرسة الملك عبدالله الثانوية";
  sync('school', "مدرسة الملك عبدالله الثانوية");
  updateEduInfo("الإدارة العامة للتعليم بمنطقة الرياض");
  
  // جلب التاريخ الهجري عند تحميل الصفحة
  await getHijriDate();
  
  // تحميل نص تجريبي عند بدء التشغيل
  setTimeout(() => {
    loadSmartText(1);
  }, 500);
};
</script>
</body>
</html>