<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أداة إعداد التقارير التعليمية</title>
<style>
/* التنسيقات الأساسية */
body {
  font-family: Tahoma, Arial, sans-serif;
  background: #eef7f5;
  margin: 0;
  padding: 20px;
  font-size: 12px;
}
.tool {
  max-width: 900px;
  margin: auto;
  background: white;
  padding: 20px;
  border-radius: 14px;
  box-shadow: 0 8px 20px rgba(0,0,0,.08);
}
.tool h2 {
  text-align: center;
  color: #0a3b40;
  margin-bottom: 16px;
  font-size: 18px;
}
label {
  font-weight: 700;
  margin-top: 12px;
  display: block;
  color: #0a3b40;
  font-size: 11px;
}
input, textarea, select {
  width: 100%;
  padding: 8px;
  margin-top: 4px;
  border-radius: 6px;
  border: 1px solid #ccc;
  font-size: 12px;
  box-sizing: border-box;
}
textarea {
  resize: none;
  height: 100px;
  overflow-y: auto;
  font-size: 10px;
  line-height: 1.4;
}
.small-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 5px;
  margin: 12px 0;
}
.small-grid input,
.small-grid select {
  font-size: 10px;
  padding: 4px 3px;
  height: 32px;
}

/* أزرار النصوص التلقائية */
.auto-row {
  display: flex;
  gap: 6px;
  margin-top: 6px;
}
.auto-btn {
  flex: 1;
  background: #e0f2f1;
  border: 1px solid #0a3b40;
  color: #0a3b40;
  font-size: 11px;
  padding: 7px;
  border-radius: 5px;
  cursor: pointer;
}
.clear-btn {
  background: #fdecea;
  border: 1px solid #c62828;
  color: #c62828;
}

/* قوائم التصنيف والتقارير */
.category-section {
  margin: 15px 0;
  padding: 10px;
  background: #f8f9fa;
  border-radius: 8px;
  border: 1px solid #ddd;
}
.category-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin-top: 10px;
}
.category-row select {
  background: white;
}

/* الزرين الرئيسيين */
.buttons-container {
  margin-top: 18px;
  display: flex;
  gap: 10px;
}
.buttons-container button {
  flex: 1;
  padding: 12px;
  border: none;
  border-radius: 8px;
  font-size: 14px;
  cursor: pointer;
  font-weight: bold;
}
#printBtn {
  background: #0a3b40;
  color: white;
}
#saveBtn {
  background: #2e7d32;
  color: white;
}

/* منطقة التقرير للطباعة */
.report {
  display: none;
}
@media print {
  body { 
    background: white; 
    padding: 0; 
    margin: 0;
    font-size: 10px;
  }
  .tool { display: none; }
  .report { 
    display: block; 
    max-width: 210mm; 
    margin: 0 auto;
    page-break-inside: avoid;
    page-break-after: avoid;
    page-break-before: avoid;
  }
}

/* الهيدر */
.header {
  background: linear-gradient(rgba(10, 59, 64, 0.9), rgba(10, 59, 64, 0.95)), 
              url('https://i.ibb.co/PsvxS5Q6/9-C92-E57-B-23-FA-479-D-A024-1-D5-F871-B4-F8-D.png');
  background-size: cover;
  background-position: center;
  color: white;
  text-align: center;
  padding: 8px 6px;
  margin-bottom: 8px;
  border-radius: 4px;
  height: 65px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}
.header-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2px;
  z-index: 2;
  width: 100%;
}
.ministry-title {
  font-size: 13pt;
  font-weight: bold;
  margin-bottom: 2px;
}
.ministry-subtitle {
  font-size: 8pt;
  margin-bottom: 4px;
}
.school-info {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1px;
}
.edu-info {
  font-weight: bold;
  font-size: 9pt;
  line-height: 1.2;
}
.school-name {
  font-weight: bold;
  font-size: 9pt;
  line-height: 1.2;
}
.hijri-date {
  font-size: 7.5pt;
  margin-top: 2px;
  color: #e0f7fa;
}

/* المربعات العلوية - ثابتة */
.top-info.two-lines {
  display: flex;
  flex-direction: column;
  gap: 3px;
  margin-bottom: 8px;
}
.top-row {
  display: grid;
  gap: 2px;
}
.top-row.first {
  grid-template-columns: repeat(3, 1fr);
}
.top-row.second {
  grid-template-columns: repeat(4, 1fr);
}
.box {
  border: 1px solid #0a3b40;
  padding: 3px;
  text-align: center;
  font-size: 6pt;
  height: 30px;
  width: 100%;
  border-radius: 2px;
  background: #f8f9fa;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.box strong {
  display: block;
  font-size: 6pt;
  color: #0a3b40;
  margin-bottom: 1px;
  line-height: 1;
}
.box div {
  font-size: 6pt;
  line-height: 1.2;
  height: 16px;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

/* المربعات الرئيسية - ثابتة تمامًا */
.fixed-box-container {
  margin-bottom: 8px;
}
.fixed-box {
  border: 1px solid #0a3b40;
  padding: 5px;
  border-radius: 5px;
  font-size: 9px;
  height: 85px;
  width: 100%;
  overflow: hidden;
  position: relative;
  background: white;
  margin-bottom: 5px;
}
.fixed-box strong {
  font-size: 9px;
  margin-bottom: 3px;
  display: block;
  color: #0a3b40;
  padding-bottom: 2px;
  border-bottom: 1px solid #eee;
}
.fixed-box-content {
  font-size: 8.5px;
  line-height: 1.3;
  height: 60px;
  overflow: hidden;
  padding-right: 2px;
  text-align: justify;
}

/* تنسيقات خاصة للمربعات */
.goal-box {
  border-right: 3px solid #2e7d32;
  background: #f1f8e9;
}
.desc-box {
  border-right: 2px solid #1565c0;
  background: #e3f2fd;
}
.results-box {
  border-right: 2px solid #ff8f00;
  background: #fff3e0;
}
.recommendations-box {
  border-right: 2px solid #6a1b9a;
  background: #f3e5f5;
}
.motivators-box {
  border-right: 2px solid #689f38;
  background: #f1f8e9;
}
.strengths-box {
  border-right: 2px solid #0277bd;
  background: #e1f5fe;
}
.challenges-box {
  border-right: 2px solid #ff8f00;
  background: #fff8e1;
}
.weaknesses-box {
  border-right: 2px solid #c62828;
  background: #ffebee;
}

/* الشبكات */
.grid2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px;
  margin-bottom: 8px;
}
.grid4 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 8px;
  margin-bottom: 8px;
}

/* الصور والتوقيعات */
.images {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin: 15px 0;
}
.images img {
  width: 100%;
  height: 150px;
  object-fit: cover;
  border-radius: 6px;
  border: 1px solid #ddd;
}
.signatures {
  margin-top: 15px;
  padding-top: 8px;
  border-top: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  font-size: 8pt;
}
.teacher-signature, .principal-signature {
  text-align: center;
  width: 45%;
}
.signature-label {
  font-weight: bold;
  color: #0a3b40;
  margin-bottom: 3px;
  font-size: 9px;
}

/* منع الانتقال للصفحة الثانية */
.page-break-protection {
  page-break-inside: avoid;
  break-inside: avoid;
}

/* إخفاء التصنيفات والتقارير في PDF */
@media print {
  .category-section,
  .auto-row,
  .tool h2 {
    display: none !important;
  }
}

/* تثبيت الأبعاد على جميع الأجهزة */
@media (max-width: 768px) {
  .small-grid {
    grid-template-columns: repeat(4, 1fr);
  }
  .grid2,
  .grid4 {
    grid-template-columns: 1fr;
  }
  .fixed-box {
    height: 85px;
    font-size: 9px;
  }
  .fixed-box-content {
    height: 60px;
    font-size: 8.5px;
  }
  .box {
    height: 30px;
    font-size: 6pt;
  }
}
</style>
</head>
<body>

<div class="tool">
<h2>أداة إعداد التقارير التعليمية (نموذج تجريبي)</h2>

<!-- خانة تصنيف التقارير -->
<div class="category-section">
  <label>تصنيف التقارير</label>
  <select id="categorySelect" onchange="updateReportsList()">
    <option value="">اختر تصنيف التقرير</option>
    <option value="strategies">استراتيجيات التدريس والتعلم</option>
    <option value="lessons">تنفيذ الدروس والشرح</option>
    <option value="technology">الوسائل والتقنيات التعليمية</option>
    <option value="activities">الأنشطة الصفية واللاصفية</option>
    <option value="support">الخطط العلاجية والدعم التعليمي</option>
    <option value="evaluation">التقويم والرصد والتحليل</option>
    <option value="questions">إعداد الأسئلة والاختبارات</option>
    <option value="supervision">المتابعة والإشراف والسلوك</option>
    <option value="shifts">المناوبة وحصص الانتظار</option>
    <option value="professional">التقارير المهنية للمعلم</option>
  </select>

  <div class="category-row">
    <div>
      <label>اختر التقرير</label>
      <select id="reportSelect" onchange="sync('reportTitle',this.value)">
        <option value="">اختر التقرير أولاً</option>
      </select>
    </div>
    <div>
      <label>نوع التقرير</label>
      <select id="typeSelect" onchange="sync('reportType',this.value)">
        <option value="">اختر نوع التقرير</option>
        <option value="تقرير نشاط إثرائي" selected>تقرير نشاط إثرائي</option>
        <option value="تقرير خطة علاجية">تقرير خطة علاجية</option>
        <option value="تقرير تنفيذ">تقرير تنفيذ</option>
        <option value="تقرير متابعة">تقرير متابعة</option>
        <option value="تقرير تحليل">تقرير تحليل</option>
      </select>
    </div>
  </div>
</div>

<label>إدارة التعليم</label>
<select id="eduSelect" onchange="updateEduInfo(this.value)">
  <option value="">اختر إدارة التعليم</option>
  <option value="الإدارة العامة للتعليم بمنطقة الرياض" selected>الإدارة العامة للتعليم بمنطقة الرياض</option>
  <option value="الإدارة العامة للتعليم بمنطقة مكة المكرمة">الإدارة العامة للتعليم بمنطقة مكة المكرمة</option>
  <option value="الإدارة العامة للتعليم بمنطقة المدينة المنورة">الإدارة العامة للتعليم بمنطقة المدينة المنورة</option>
</select>

<label>اسم المدرسة</label>
<input id="schoolInput" placeholder="أدخل اسم المدرسة هنا" oninput="sync('school',this.value)">

<div class="small-grid">
  <input placeholder="المستهدفون" oninput="sync('target',this.value)" maxlength="25">
  <input placeholder="العدد" oninput="sync('count',this.value)" maxlength="8">
  <input placeholder="مكان التنفيذ" oninput="sync('location',this.value)" maxlength="30">
  <select id="semesterSelect" onchange="sync('semester',this.value)">
    <option value="">اختر الفصل الدراسي</option>
    <option value="الفصل الدراسي الأول">الفصل الدراسي الأول</option>
    <option value="الفصل الدراسي الثاني">الفصل الدراسي الثاني</option>
  </select>
  <input placeholder="الصف" oninput="sync('grade',this.value)" maxlength="15">
  <input placeholder="المادة" oninput="sync('subject',this.value)" maxlength="20">
  <input placeholder="تاريخ التقرير" oninput="sync('reportDate',this.value)" maxlength="15">
</div>

<!-- اختيار النص التلقائي -->
<div class="auto-row">
  <button class="auto-btn" onclick="loadSmartText(1)">نص تلقائي 1</button>
  <button class="auto-btn" onclick="loadSmartText(2)">نص تلقائي 2</button>
  <button class="auto-btn" onclick="loadSmartText(3)">نص تلقائي 3</button>
  <button class="auto-btn" onclick="loadSmartText(4)">نص تلقائي 4</button>
  <button class="auto-btn" onclick="loadSmartText(5)">نص تلقائي 5</button>
  <button class="clear-btn" onclick="clearAllFields()">مسح الحقول</button>
</div>

<!-- المربعات الثابتة -->
<div class="fixed-box-container">
  <label>الهدف التربوي (محدد 15 كلمة)</label>
  <div class="fixed-box goal-box">
    <strong>الهدف التربوي</strong>
    <div class="fixed-box-content" id="goal"></div>
  </div>
  <textarea id="goalInput" oninput="syncFixed('goal',this.value)" maxlength="100" 
            placeholder="أدخل الهدف التربوي (حد أقصى 15 كلمة)"></textarea>
</div>

<div class="grid2">
  <div>
    <label>وصف مختصر (محدد 15 كلمة)</label>
    <div class="fixed-box desc-box">
      <strong>وصف مختصر</strong>
      <div class="fixed-box-content" id="desc1"></div>
    </div>
    <textarea id="desc1Input" oninput="syncFixed('desc1',this.value)" maxlength="100"></textarea>
  </div>
  <div>
    <label>إجراءات التنفيذ (محدد 15 كلمة)</label>
    <div class="fixed-box desc-box">
      <strong>إجراءات التنفيذ</strong>
      <div class="fixed-box-content" id="desc2"></div>
    </div>
    <textarea id="desc2Input" oninput="syncFixed('desc2',this.value)" maxlength="100"></textarea>
  </div>
</div>

<div class="grid2">
  <div>
    <label>النتائج (محدد 15 كلمة)</label>
    <div class="fixed-box results-box">
      <strong>النتائج</strong>
      <div class="fixed-box-content" id="desc3"></div>
    </div>
    <textarea id="desc3Input" oninput="syncFixed('desc3',this.value)" maxlength="100"></textarea>
  </div>
  <div>
    <label>التوصيات (محدد 15 كلمة)</label>
    <div class="fixed-box recommendations-box">
      <strong>التوصيات</strong>
      <div class="fixed-box-content" id="desc4"></div>
    </div>
    <textarea id="desc4Input" oninput="syncFixed('desc4',this.value)" maxlength="100"></textarea>
  </div>
</div>

<div class="grid4">
  <div>
    <label>المحفزات (محدد 15 كلمة)</label>
    <div class="fixed-box motivators-box">
      <strong>المحفزات</strong>
      <div class="fixed-box-content" id="motivators"></div>
    </div>
    <textarea id="motivatorsInput" oninput="syncFixed('motivators',this.value)" maxlength="100"></textarea>
  </div>
  <div>
    <label>نقاط القوة (محدد 15 كلمة)</label>
    <div class="fixed-box strengths-box">
      <strong>نقاط القوة</strong>
      <div class="fixed-box-content" id="strengths"></div>
    </div>
    <textarea id="strengthsInput" oninput="syncFixed('strengths',this.value)" maxlength="100"></textarea>
  </div>
  <div>
    <label>التحديات (محدد 15 كلمة)</label>
    <div class="fixed-box challenges-box">
      <strong>التحديات</strong>
      <div class="fixed-box-content" id="challenges"></div>
    </div>
    <textarea id="challengesInput" oninput="syncFixed('challenges',this.value)" maxlength="100"></textarea>
  </div>
  <div>
    <label>مواطن القصور (محدد 15 كلمة)</label>
    <div class="fixed-box weaknesses-box">
      <strong>مواطن القصور</strong>
      <div class="fixed-box-content" id="weaknesses"></div>
    </div>
    <textarea id="weaknessesInput" oninput="syncFixed('weaknesses',this.value)" maxlength="100"></textarea>
  </div>
</div>

<label>إرفاق الصور (اختياري - الحد الأقصى: صورتين)</label>
<input type="file" multiple accept="image/*" onchange="loadImages(this)">

<div class="signatures">
  <div class="teacher-signature">
    <div class="signature-label">اسم المعلم</div>
    <input type="text" id="teacherInput" placeholder="أدخل اسم المعلم" oninput="sync('teacherName', this.value)" maxlength="40">
  </div>
  <div class="principal-signature">
    <div class="signature-label">اسم مدير المدرسة</div>
    <input type="text" id="principalInput" placeholder="أدخل اسم المدير" oninput="sync('principalName', this.value)" maxlength="40">
  </div>
</div>

<div class="buttons-container">
  <button id="printBtn" onclick="window.print()">🖨️ طباعة التقرير</button>
  <button id="saveBtn" onclick="saveReport()">💾 حفظ التقرير</button>
</div>
</div>

<!-- قسم التقرير للطباعة -->
<div class="report page-break-protection" id="reportContent">
<div class="header page-break-protection">
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

<div class="top-info two-lines page-break-protection">
  <div class="top-row first page-break-protection">
    <div class="box page-break-protection"><strong>الفصل الدراسي</strong><div id="semester"></div></div>
    <div class="box page-break-protection"><strong>الصف</strong><div id="grade"></div></div>
    <div class="box page-break-protection"><strong>المادة</strong><div id="subject"></div></div>
  </div>
  <div class="top-row second page-break-protection">
    <div class="box page-break-protection"><strong>نوع التقرير</strong><div id="reportType"></div></div>
    <div class="box page-break-protection"><strong>المستهدفون</strong><div id="target"></div></div>
    <div class="box page-break-protection"><strong>العدد</strong><div id="count"></div></div>
    <div class="box page-break-protection"><strong>مكان التنفيذ</strong><div id="location"></div></div>
  </div>
  <div class="top-row first page-break-protection">
    <div class="box page-break-protection"><strong>التقرير</strong><div id="reportTitle"></div></div>
    <div class="box page-break-protection"><strong>التاريخ</strong><div id="reportDate"></div></div>
    <div class="box page-break-protection"><strong>المعلم</strong><div id="teacherName"></div></div>
  </div>
</div>

<div class="fixed-box goal-box page-break-protection">
  <strong>الهدف التربوي</strong>
  <div class="fixed-box-content" id="goalPrint"></div>
</div>

<div class="grid2 page-break-protection">
  <div class="fixed-box desc-box page-break-protection">
    <strong>وصف مختصر</strong>
    <div class="fixed-box-content" id="desc1Print"></div>
  </div>
  <div class="fixed-box desc-box page-break-protection">
    <strong>إجراءات التنفيذ</strong>
    <div class="fixed-box-content" id="desc2Print"></div>
  </div>
</div>

<div class="grid2 page-break-protection">
  <div class="fixed-box results-box page-break-protection">
    <strong>النتائج</strong>
    <div class="fixed-box-content" id="desc3Print"></div>
  </div>
  <div class="fixed-box recommendations-box page-break-protection">
    <strong>التوصيات</strong>
    <div class="fixed-box-content" id="desc4Print"></div>
  </div>
</div>

<div class="grid4 page-break-protection">
  <div class="fixed-box motivators-box page-break-protection">
    <strong>المحفزات</strong>
    <div class="fixed-box-content" id="motivatorsPrint"></div>
  </div>
  <div class="fixed-box strengths-box page-break-protection">
    <strong>نقاط القوة</strong>
    <div class="fixed-box-content" id="strengthsPrint"></div>
  </div>
  <div class="fixed-box challenges-box page-break-protection">
    <strong>التحديات</strong>
    <div class="fixed-box-content" id="challengesPrint"></div>
  </div>
  <div class="fixed-box weaknesses-box page-break-protection">
    <strong>مواطن القصور</strong>
    <div class="fixed-box-content" id="weaknessesPrint"></div>
  </div>
</div>

<div class="images page-break-protection" id="imagesBox"></div>

<div class="signatures page-break-protection">
  <div class="teacher-signature">
    <div class="signature-label">المعلم</div>
    <div id="teacherNamePrint"></div>
  </div>
  <div class="principal-signature">
    <div class="signature-label">مدير المدرسة</div>
    <div id="principalNamePrint"></div>
  </div>
</div>
</div>

<script>
// قاعدة البيانات للتقارير
const reportsDatabase = {
  strategies: [
    "تقرير تطبيق التعلم النشط",
    "تقرير استراتيجية التعلم التعاوني",
    "تقرير استراتيجية حل المشكلات",
    "تقرير استراتيجية العصف الذهني",
    "تقرير استراتيجية التفكير الناقد",
    "تقرير استراتيجية التفكير الإبداعي",
    "تقرير استراتيجية التعلم القائم على المشروع",
    "تقرير استراتيجية التعلم القائم على الاستقصاء",
    "تقرير استراتيجية الفصول المقلوبة",
    "تقرير استراتيجية التعلم باللعب",
    "تقرير استراتيجية التعلم الذاتي",
    "تقرير استراتيجية القبعات الست",
    "تقرير استراتيجية الخرائط الذهنية",
    "تقرير استراتيجية التعليم المتمايز"
  ],
  lessons: [
    "تقرير درس تم تنفيذه",
    "تقرير تنفيذ درس تطبيقي",
    "تقرير توزيع وقت الحصة",
    "تقرير تطوير البيئة الصفية"
  ],
  technology: [
    "تقرير استخدام الوسائل التعليمية",
    "تقرير إنتاج وسائل تعليمية مبتكرة",
    "تقرير توظيف الوسائل الرقمية",
    "تقرير استخدام العروض التقديمية",
    "تقرير استخدام السبورة التفاعلية",
    "تقرير توظيف الفيديو التعليمي",
    "تقرير استخدام التطبيقات التعليمية",
    "تقرير استخدام المنصات التعليمية",
    "تقرير تصميم أوراق عمل تفاعلية",
    "تقرير توظيف الذكاء الاصطناعي في التعليم"
  ],
  activities: [
    "تقرير تنفيذ أنشطة صفية",
    "تقرير أنشطة إثرائية",
    "تقرير أنشطة علاجية صفية",
    "تقرير الأنشطة اللاصفية",
    "تقرير حصص النشاط",
    "تقرير المبادرات الطلابية",
    "تقرير المسابقات والمشاركات الطلابية",
    "تقرير المشاركات بين الطلاب",
    "تقرير تنفيذ إذاعة مدرسية",
    "تقرير المعلم الصغير"
  ],
  support: [
    "تقرير إعداد وتنفيذ خطة علاجية",
    "تقرير متابعة ونتائج الخطة العلاجية",
    "تقرير علاج ضعف القراءة",
    "تقرير علاج ضعف الكتابة",
    "تقرير علاج ضعف الحساب",
    "تقرير دعم الطلاب المتأخرين دراسيًا",
    "تقرير التدخل العلاجي المبكر",
    "تقرير الإثراء للطلاب المتفوقين",
    "تقرير دراسة حالة طالب",
    "تقرير حل مشكلة تربوية"
  ],
  evaluation: [
    "تقرير إعداد أدوات التقويم",
    "تقرير التقويم التشخيصي",
    "تقرير التقويم البنائي",
    "تقرير التقويم الختامي",
    "تقرير تحليل نتائج الاختبارات",
    "تقرير متابعة مستوى التحصيل",
    "تقرير مقارنة نتائج الفترات",
    "تقرير قياس نواتج التعلم",
    "تقرير رصد وتصحيح الدرجات",
    "تقرير التغذية الراجعة للطلاب"
  ],
  questions: [
    "تقرير إعداد بنك أسئلة",
    "تقرير تنويع مستويات الأسئلة",
    "تقرير مواءمة الأسئلة مع الأهداف",
    "تقرير تحليل الأسئلة (الصعوبة والتمييز)",
    "تقرير الاختبارات الإلكترونية",
    "تقرير الاختبارات الذكية",
    "تقرير تنفيذ اختبار تحسن"
  ],
  supervision: [
    "تقرير كشف المتابعة",
    "تقرير سجل الدرجات الإلكتروني",
    "تقرير سجل التغذية الراجعة من الطلاب",
    "تقرير متابعة الانضباط والسلوك",
    "تقرير متابعة الغياب والتأخر",
    "تقرير ضبط الصف",
    "تقرير تعزيز السلوك الإيجابي",
    "تقرير تحفيز الطلاب",
    "تقرير معرفة الميول والاتجاهات"
  ],
  shifts: [
    "تقرير المناوبة المدرسية",
    "تقرير الإشراف اليومي والأسبوعي",
    "تقرير الإشراف على الفسحة",
    "تقرير حصص الانتظار التعليمية"
  ],
  professional: [
    "تقرير التدريب على الاختبارات المعيارية",
    "تقرير حضور دورات وورش تدريبية",
    "تقرير نقل أثر التدريب",
    "تقرير الورش التدريبية التي قدمتها",
    "تقرير البحث الإجرائي"
  ]
};

// قاعدة البيانات للنصوص الذكية (5 نصوص لكل فئة)
const smartTextsDatabase = {
  1: {
    goal: "تنمية مهارات التفكير النقدي والإبداعي لدى الطلاب من خلال أنشطة تفاعلية متنوعة تناسب قدراتهم المختلفة.",
    desc1: "تم تطبيق استراتيجيات التعلم النشط لتحفيز المشاركة الطلابية وتنمية مهارات التفكير العليا والتحليل الناقد.",
    desc2: "تنفيذ جلسات تعلم تعاوني وحلقات نقاش ومشاريع جماعية مع توفير أدوات التقويم المستمر والتغذية الراجعة الفورية.",
    desc3: "تحسن ملحوظ في مشاركة الطلاب وارتفاع مستوى التفكير الناقد وزيادة الثقة بالنفس وتعزيز روح التعاون بينهم.",
    desc4: "توسيع تطبيق الاستراتيجيات وتدريب المعلمين وتوفير الأدوات اللازمة ومتابعة الأثر على التحصيل الدراسي.",
    motivators: "جوائز رمزية وشهادات تقدير ومشاركة في المعارض ونشر الإنجازات وتقدير الأداء المتميز.",
    strengths: "كفاءة المعلمين وتوافر المصادر ودعم الإدارة وتفاعل الطلاب وجودة التخطيط والتنفيذ.",
    challenges: "محدودية الوقت واختلاف المستويات وصعوبة التقويم ونقص الموارد ومقاومة التغيير.",
    weaknesses: "نقص الخبرات ومحدودية التدريب وضعف المتابعة وقلة الأدوات وصعوبة القياس الكمي."
  },
  2: {
    goal: "تحسين المستوى التحصيلي للطلاب عبر معالجة الصعوبات التعلمية باستخدام خطط علاجية فردية وجماعية مناسبة.",
    desc1: "تم تشخيص الصعوبات التعلمية للطلاب المتأخرين وتصميم برامج علاجية مكثفة تناسب احتياجاتهم الفردية.",
    desc2: "تطبيق جلسات علاجية مكثفة وأنشطة تصحيحية وتدريبات عملية مع متابعة أسرية وتقويم دوري للتقدم.",
    desc3: "تحسن كبير في المستوى التحصيلي وارتفاع درجات الطلاب وزيادة الدافعية للتعلم وتحسن الثقة بالنفس.",
    desc4: "استمرارية البرامج العلاجية وتطوير الأدوات وتدريب الكوادر وتعزيز الشراكة الأسرية والتوسع في التطبيق.",
    motivators: "برامج تحفيزية وجوائز تقدم وشهادات تقدير ونشر النجاحات وزيادة الثقة والمكافآت التشجيعية.",
    strengths: "تخصص المعلمين وجودة الخطة وتوافر المصادر ودعم الإدارة وتفاعل أولياء الأمور والإشراف المباشر.",
    challenges: "تفاوت الصعوبات ومقاومة الطلاب وضيق الوقت وضعف المتابعة الأسرية وصعوبة التشخيص الدقيق.",
    weaknesses: "قلة المتخصصين ومحدودية الموارد وصعوبة القياس ونقص التدريب وضعف التنسيق بين الأطراف."
  },
  3: {
    goal: "توظيف التقنيات الحديثة في العملية التعليمية لتحسين جودة التعليم وزيادة تفاعل الطلاب مع المحتوى الدراسي.",
    desc1: "تم دمج الوسائل التقنية الحديثة في التدريس واستخدام المنصات التعليمية والتطبيقات التفاعلية في الشرح.",
    desc2: "استخدام السبورة التفاعلية وتطبيقات الجوال والعروض المتقدمة والفيديو التعليمي مع تدريب الطلاب على الاستخدام.",
    desc3: "زيادة تفاعل الطلاب وتحسن الفهم وسرعة التعلم وارتفاع التحصيل وتنمية المهارات التقنية لدى الجميع.",
    desc4: "توسيع استخدام التقنية وتحديث الأجهزة وتدريب المعلمين وتطوير المحتوى الرقمي ودعم البنية التحتية.",
    motivators: "تشجيع الاستخدام والمسابقات التقنية ونشر التجارب والجوائز التشجيعية والاعتراف بالمتميزين.",
    strengths: "توافر الأجهزة وكفاءة المعلمين ودعم الإدارة وتفاعل الطلاب وجودة المحتوى الرقمي المتاح.",
    challenges: "صعوبة الصيانة وسرعة التقادم ونقص التدريب واختلاف المهارات ومشاكل الاتصال والإنترنت.",
    weaknesses: "قلة الخبرات وارتفاع التكلفة وصعوبة التطوير ونقص الدعم الفني ومحدودية البرامج العربية."
  },
  4: {
    goal: "تنفيذ أنشطة صفية ولاصفية متنوعة لتنمية المهارات الحياتية وتعزيز القيم والهوية الوطنية لدى الطلاب.",
    desc1: "تم تنظيم أنشطة تعليمية وترفيهية ورياضية وثقافية داخل الصف وخارجه لتحقيق أهداف تربوية شاملة.",
    desc2: "إقامة مسابقات وأنشطة تطوعية ومعارض ومبادرات طلابية مع تخطيط زمني دقيق وتقويم للأثر التربوي.",
    desc3: "تنمية المهارات الاجتماعية وزيادة الانتماء وتحسين الصحة النفسية ورفع الروح المعنوية وتعزيز القيم.",
    desc4: "استمرارية الأنشطة وتنويعها وتدريب القيادات الطلابية وتوثيق التجارب وتوسيع قاعدة المشاركة.",
    motivators: "شهادات مشاركة وجوائز للمتميزين ونشر الإنجازات والرحلات الترفيهية والتكريم العلني والدعم المعنوي.",
    strengths: "تنوع الأنشطة ودعم الإدارة وتفاعل الطلاب وجودة التخطيط وتوافر المكان والموارد المناسبة.",
    challenges: "ضيق الوقت ومحدودية الميزانية وصعوبة التنظيم ومشاكل الأمن والسلامة واختلاف الرغبات.",
    weaknesses: "قلة المدربين وضعف البنية التحتية وصعوبة التقييم ومحدودية الدعم وعدم الاستمرارية."
  },
  5: {
    goal: "تطوير أدوات التقويم وتحليل النتائج لقياس نواتج التعلم وتحسين العملية التعليمية بناءً على البيانات.",
    desc1: "تم تصميم وتطبيق أدوات تقويم متنوعة تشمل تقويم تشخيصي وبنائي وختامي لقياس تقدم الطلاب بدقة.",
    desc2: "إعداد اختبارات وتحليل نتائج ومقارنة الأداء ورصد الدرجات وتقديم تغذية راجعة وتعديل الخطط.",
    desc3: "تحسن دقة القياس ووضوح نقاط القوة والضعف وارتفاع مستوى التحصيل وتحسين جودة التعليم والتعلم.",
    desc4: "تطوير بنك الأسئلة وتدريب المعلمين على التقويم واستخدام التقنية في التحليل وتعزيز ثقافة التقويم.",
    motivators: "تحسين الدرجات ووضوح التقدم والدعم الفني والتقدير المهني والمشاركة في صنع القرار التربوي.",
    strengths: "دقة الأدوات وكفاءة المعلمين ودعم الإدارة وتوافر البيانات واستخدام التقنية في التحليل.",
    challenges: "صعوبة الإعداد وضيق الوقت واختلاف المعايير ومقاومة التغيير وصعوبة تحليل البيانات الكبيرة.",
    weaknesses: "نقص الخبرات ومحدودية الأدوات وصعوبة التطبيق وضعف المتابعة وقلة التدريب المتخصص."
  }
};

// تحديث قائمة التقارير بناءً على التصنيف
function updateReportsList() {
  const category = document.getElementById('categorySelect').value;
  const reportSelect = document.getElementById('reportSelect');
  
  // مسح الخيارات الحالية
  reportSelect.innerHTML = '<option value="">اختر التقرير أولاً</option>';
  
  if (category && reportsDatabase[category]) {
    reportsDatabase[category].forEach(report => {
      const option = document.createElement('option');
      option.value = report;
      option.textContent = report;
      reportSelect.appendChild(option);
    });
  }
}

// قص النص ليلائم المربعات الثابتة
function truncateForBox(text, wordLimit = 15) {
  if (!text) return '';
  const words = text.split(' ');
  if (words.length <= wordLimit) return text;
  return words.slice(0, wordLimit).join(' ') + '...';
}

// مزامنة الحقول مع المربعات الثابتة
function syncFixed(id, value) {
  const displayElement = document.getElementById(id);
  const printElement = document.getElementById(id + 'Print');
  
  if (displayElement) {
    displayElement.textContent = truncateForBox(value);
  }
  if (printElement) {
    printElement.textContent = truncateForBox(value);
  }
}

// مزامنة الحقول العادية
function sync(id, value) {
  const el = document.getElementById(id);
  const printEl = document.getElementById(id + 'Print');
  
  if (el) el.textContent = truncateForBox(value, 10);
  if (printEl) printEl.textContent = truncateForBox(value, 10);
}

// دالة لتحديث معلومات إدارة التعليم
function updateEduInfo(value) {
  const eduHeader = document.getElementById('eduHeader');
  if (eduHeader && value) {
    eduHeader.textContent = truncateForBox(value, 8);
  }
}

// دالة لتحميل النص الذكي
function loadSmartText(textNumber) {
  const textData = smartTextsDatabase[textNumber];
  if (!textData) {
    alert("النص غير متوفر");
    return;
  }
  
  // تعبئة جميع الحقول
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
  syncFixed('goal', textData.goal);
  syncFixed('desc1', textData.desc1);
  syncFixed('desc2', textData.desc2);
  syncFixed('desc3', textData.desc3);
  syncFixed('desc4', textData.desc4);
  syncFixed('motivators', textData.motivators);
  syncFixed('strengths', textData.strengths);
  syncFixed('challenges', textData.challenges);
  syncFixed('weaknesses', textData.weaknesses);
  
  alert(`تم تحميل النص التلقائي ${textNumber} بنجاح!`);
}

// مسح جميع الحقول
function clearAllFields() {
  const textareas = document.querySelectorAll('textarea');
  const inputs = document.querySelectorAll('input[type="text"]');
  
  textareas.forEach(ta => ta.value = '');
  inputs.forEach(input => input.value = '');
  
  // مسح المربعات
  const boxes = ['goal', 'desc1', 'desc2', 'desc3', 'desc4', 'motivators', 'strengths', 'challenges', 'weaknesses'];
  boxes.forEach(box => {
    syncFixed(box, '');
    sync(box, '');
  });
  
  // مسح الصور
  document.getElementById('imagesBox').innerHTML = '';
  
  // إعادة التعيين
  document.getElementById('reportSelect').selectedIndex = 0;
  document.getElementById('typeSelect').selectedIndex = 0;
  document.getElementById('categorySelect').selectedIndex = 0;
  document.getElementById('semesterSelect').selectedIndex = 0;
  
  sync('reportTitle', '');
  sync('reportType', '');
  sync('target', '');
  sync('count', '');
  sync('location', '');
  sync('grade', '');
  sync('subject', '');
  sync('reportDate', '');
  sync('teacherName', '');
  sync('principalName', '');
  sync('semester', '');
}

// تحميل الصور
function loadImages(input) {
  const box = document.getElementById("imagesBox");
  box.innerHTML = "";
  const files = Array.from(input.files).slice(0, 2);
  
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

// الحصول على التاريخ الهجري
async function getHijriDate() {
  try {
    const today = new Date();
    const options = { calendar: 'islamic', year: 'numeric', month: 'long', day: 'numeric' };
    const hijriDate = new Intl.DateTimeFormat('ar-SA', options).format(today);
    document.getElementById('hijriDate').textContent = `التاريخ الهجري: ${hijriDate}`;
  } catch (error) {
    document.getElementById('hijriDate').textContent = "التاريخ الهجري: غير متاح";
  }
}

// حفظ التقرير
function saveReport() {
  const reportTitle = document.getElementById('reportTitle').textContent;
  if (!reportTitle || reportTitle === '') {
    alert("الرجاء اختيار وتعبئة بيانات التقرير أولاً");
    return;
  }
  
  // هنا يمكن إضافة منطق لحفظ التقرير في قاعدة بيانات أو ملف
  alert("تم حفظ التقرير بنجاح!\n\nملاحظة: هذه ميزة تجريبية، في النسخة النهائية سيتم حفظ التقرير في قاعدة البيانات.");
}

// التهيئة عند التحميل
window.onload = async function() {
  // تعبئة البيانات الافتراضية
  document.getElementById('schoolInput').value = "مدرسة التجربة النموذجية";
  sync('school', "مدرسة التجربة النموذجية");
  updateEduInfo("الإدارة العامة للتعليم بمنطقة الرياض");
  
  // جلب التاريخ الهجري
  await getHijriDate();
  
  // تحميل نص تجريبي
  setTimeout(() => {
    loadSmartText(1);
  }, 500);
  
  // إعداد التاريخ الحالي
  const today = new Date();
  const dateStr = `${today.getDate()}/${today.getMonth() + 1}/${today.getFullYear()}`;
  document.querySelector('input[placeholder="تاريخ التقرير"]').value = dateStr;
  sync('reportDate', dateStr);
};
</script>
</body>
</html>
