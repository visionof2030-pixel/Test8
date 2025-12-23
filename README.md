
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أداة إعداد التقارير التعليمية (نموذج تجريبي)</title>
<style>
/* تصميم النموذج التفاعلي */
body {
  font-family: 'Segoe UI', Tahoma, Arial, sans-serif;
  background: linear-gradient(135deg, #eef7f5 0%, #e0f2f1 100%);
  margin: 0;
  padding: 20px;
  font-size: 14px;
  color: #0a3b40;
  min-height: 100vh;
}

.tool {
  max-width: 1100px;
  margin: auto;
  background: white;
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 15px 40px rgba(10, 59, 64, 0.15);
  border: 1px solid rgba(10, 59, 64, 0.1);
}

.tool h2 {
  text-align: center;
  color: #0a3b40;
  margin-bottom: 25px;
  font-size: 24px;
  padding-bottom: 15px;
  border-bottom: 3px solid #e0f2f1;
  position: relative;
}

.tool h2:after {
  content: '';
  position: absolute;
  bottom: -3px;
  right: 45%;
  width: 10%;
  height: 3px;
  background: #0a3b40;
}

.form-section {
  margin-bottom: 30px;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 15px;
  border: 2px solid #e0f2f1;
}

.section-title {
  font-size: 16px;
  color: #0a3b40;
  margin-bottom: 15px;
  padding-bottom: 8px;
  border-bottom: 2px solid #0a3b40;
  font-weight: bold;
}

label {
  font-weight: 700;
  margin-top: 15px;
  display: block;
  color: #0a3b40;
  font-size: 13px;
}

.input-hint {
  font-size: 11px;
  color: #689f38;
  margin-top: 4px;
  margin-bottom: 8px;
  font-weight: normal;
  background: #f1f8e9;
  padding: 6px 10px;
  border-radius: 6px;
  border-right: 3px solid #689f38;
}

/* تحسين أحجام الحقول */
input, textarea, select {
  width: 100%;
  padding: 14px;
  margin-top: 6px;
  border-radius: 10px;
  border: 2px solid #b0bec5;
  font-size: 15px;
  box-sizing: border-box;
  transition: all 0.3s ease;
  background: white;
}

input:focus, textarea:focus, select:focus {
  outline: none;
  border-color: #0a3b40;
  box-shadow: 0 0 0 4px rgba(10, 59, 64, 0.15);
  background: #fff;
}

/* زيادة حجم حقول النصوص */
textarea {
  resize: vertical;
  min-height: 100px;
  max-height: 200px;
  overflow-y: auto;
  line-height: 1.6;
  font-size: 14px;
}

/* تحسين حجم حقول الشبكة الصغيرة */
.small-grid {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  gap: 12px;
  margin: 20px 0;
  background: white;
  padding: 15px;
  border-radius: 12px;
  border: 2px solid #e0e0e0;
}

.small-grid input,
.small-grid select {
  font-size: 13px;
  padding: 12px 8px;
  height: 48px;
}

/* تحسين الأزرار */
.auto-row {
  display: flex;
  gap: 10px;
  margin-top: 15px;
  margin-bottom: 12px;
}

.auto-btn {
  flex: 1;
  background: linear-gradient(135deg, #e0f2f1 0%, #b2dfdb 100%);
  border: 2px solid #0a3b40;
  color: #0a3b40;
  font-size: 14px;
  padding: 14px;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 600;
  height: 55px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.auto-btn:hover {
  background: linear-gradient(135deg, #0a3b40 0%, #0d4a50 100%);
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 6px 15px rgba(10, 59, 64, 0.25);
}

.clear-btn {
  background: linear-gradient(135deg, #fdecea 0%, #ffcdd2 100%);
  border: 2px solid #c62828;
  color: #c62828;
}

.clear-btn:hover {
  background: linear-gradient(135deg, #c62828 0%, #b71c1c 100%);
  color: white;
}

button#printBtn {
  margin-top: 30px;
  padding: 18px;
  width: 100%;
  background: linear-gradient(135deg, #0a3b40 0%, #0d4a50 100%);
  color: white;
  border: none;
  border-radius: 12px;
  font-size: 18px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: bold;
  letter-spacing: 1px;
  height: 65px;
}

button#printBtn:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 20px rgba(10, 59, 64, 0.35);
}

/* تنسيق الإمضاءات */
.signatures {
  margin-top: 25px;
  padding-top: 15px;
  border-top: 2px solid #ccc;
  display: flex;
  justify-content: space-between;
  font-size: 14px;
  gap: 20px;
}

.teacher-signature, .principal-signature {
  text-align: center;
  width: 48%;
  padding: 15px;
  background: white;
  border-radius: 10px;
  border: 2px solid #e0f2f1;
}

.teacher-signature input, .principal-signature input {
  width: 90%;
  font-size: 15px;
  padding: 10px;
  margin-top: 10px;
  border: none;
  border-bottom: 2px solid #ccc;
  text-align: center;
  background: transparent;
  font-size: 16px;
}

.signature-label {
  font-weight: bold;
  color: #0a3b40;
  margin-bottom: 8px;
  font-size: 15px;
}

/* قسم صور المعاينة (غير مطبوع) */
.preview-images {
  margin: 20px 0;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 12px;
  border: 2px dashed #b0bec5;
}

.preview-images h3 {
  color: #0a3b40;
  margin-bottom: 15px;
  text-align: center;
}

.image-container {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
  justify-content: center;
}

.preview-img {
  width: 300px;
  height: 200px;
  object-fit: cover;
  border-radius: 10px;
  border: 3px solid #e0f2f1;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

/* تنسيق التقرير للطباعة - بدون تغيير */
.report {
  display: none;
}

@media print {
  body { 
    background: white; 
    padding: 0; 
    margin: 0;
    font-size: 10px !important;
  }
  
  .tool { 
    display: none; 
  }
  
  .report { 
    display: block; 
    max-width: 210mm; 
    margin: 0 auto; 
    padding: 10mm;
    box-sizing: border-box;
    page-break-inside: avoid;
  }
  
  /* الحفاظ على تنسيق PDF كما هو */
  .header {
    background: linear-gradient(135deg, #0a3b40 0%, #0d4a50 100%);
    color: white;
    text-align: center;
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 4px;
    min-height: auto;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    page-break-inside: avoid;
  }
  
  .header-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2px;
  }
  
  .ministry-title {
    font-size: 13pt !important;
    font-weight: bold;
    margin: 0;
  }
  
  .ministry-subtitle {
    font-size: 8pt !important;
    margin: 0;
  }
  
  .school-info {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1px;
    margin-top: 2px;
  }
  
  .edu-info {
    font-weight: bold;
    font-size: 9pt !important;
    margin: 0;
  }
  
  .school-name {
    font-weight: bold;
    font-size: 9pt !important;
    color: #e0f7fa;
    margin: 0;
  }
  
  .hijri-date {
    font-size: 8pt !important;
    margin-top: 2px;
    color: #e0f7fa;
    opacity: 0.9;
  }
  
  .top-info.two-lines {
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin-bottom: 10px;
    page-break-inside: avoid;
  }
  
  .top-row {
    display: grid;
    gap: 3px;
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
    font-size: 5.5pt !important;
    min-height: 22px;
    max-height: 35px;
    border-radius: 2px;
    background: #f8f9fa;
    overflow: hidden;
    text-overflow: ellipsis;
    page-break-inside: avoid;
  }
  
  .box strong {
    display: block;
    font-size: 5.5pt !important;
    color: #0a3b40;
    margin-bottom: 1px;
  }
  
  .box div {
    font-size: 5.5pt !important;
    line-height: 1.2;
    max-height: 25px;
    overflow: hidden;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    margin: 0;
  }
  
  .goal-section {
    background: #e8f5e9;
    border-right: 2px solid #2e7d32;
    border-radius: 5px;
    padding: 6px;
    margin-bottom: 8px;
    text-align: center;
    min-height: 40px;
    max-height: 60px;
    overflow: hidden;
    page-break-inside: avoid;
  }
  
  .goal-section strong {
    font-size: 9px !important;
    margin-bottom: 2px;
    color: #1b5e20;
  }
  
  .goal-section div {
    font-size: 8px !important;
    line-height: 1.3;
    max-height: 40px;
    overflow: hidden;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    margin: 0;
  }
  
  .grid2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
    margin-bottom: 8px;
    page-break-inside: avoid;
  }
  
  .grid4 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
    margin-bottom: 8px;
    page-break-inside: avoid;
  }
  
  .section {
    border: 1px solid #0a3b40;
    padding: 4px;
    border-radius: 4px;
    font-size: 7px !important;
    max-height: 80px;
    overflow: hidden;
    page-break-inside: avoid;
  }
  
  .section strong {
    font-size: 8px !important;
    margin-bottom: 2px;
    display: block;
    color: #0a3b40;
  }
  
  .section div {
    font-size: 7px !important;
    line-height: 1.3;
    max-height: 60px;
    overflow-y: auto;
    padding-right: 2px;
    margin: 0;
  }
  
  .section.motivators {
    border: 1px solid #9ccc65;
    background: #f1f8e9;
    min-height: 40px;
    max-height: 60px;
    height: auto;
    padding: 3px;
    font-size: 6.5px !important;
  }
  
  .section.motivators strong {
    font-size: 7.5px !important;
    margin-bottom: 1px;
    color: #689f38;
  }
  
  .section.motivators div {
    font-size: 6.5px !important;
    line-height: 1.2;
    max-height: 45px;
  }
  
  .section.strengths {
    border: 1px solid #0d47a1;
    background: #e3f2fd;
    min-height: 40px;
    max-height: 60px;
    height: auto;
    padding: 3px;
    font-size: 6.5px !important;
  }
  
  .section.strengths strong {
    font-size: 7.5px !important;
    margin-bottom: 1px;
    color: #0d47a1;
  }
  
  .section.strengths div {
    font-size: 6.5px !important;
    line-height: 1.2;
    max-height: 45px;
  }
  
  .section.challenges {
    border: 1px solid #f57f17;
    background: #fffde7;
    min-height: 40px;
    max-height: 60px;
    height: auto;
    padding: 3px;
    font-size: 6.5px !important;
  }
  
  .section.challenges strong {
    font-size: 7.5px !important;
    margin-bottom: 1px;
    color: #f57f17;
  }
  
  .section.challenges div {
    font-size: 6.5px !important;
    line-height: 1.2;
    max-height: 45px;
  }
  
  .section.weaknesses {
    border: 1px solid #c62828;
    background: #ffebee;
    min-height: 40px;
    max-height: 60px;
    height: auto;
    padding: 3px;
    font-size: 6.5px !important;
  }
  
  .section.weaknesses strong {
    font-size: 7.5px !important;
    margin-bottom: 1px;
    color: #c62828;
  }
  
  .section.weaknesses div {
    font-size: 6.5px !important;
    line-height: 1.2;
    max-height: 45px;
  }
  
  /* تحديد مساحة الصور في PDF */
  .images {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
    margin: 10px 0;
    max-height: 150px;
    page-break-inside: avoid;
  }
  
  .images img {
    width: 100%;
    height: 140px;
    object-fit: cover;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    border: 1px solid #ddd;
  }
  
  .signatures {
    margin-top: 10px;
    padding-top: 6px;
    border-top: 1px solid #ccc;
    display: flex;
    justify-content: space-between;
    font-size: 8pt !important;
    page-break-inside: avoid;
  }
  
  .teacher-signature, .principal-signature {
    text-align: center;
    width: 45%;
    padding: 0;
    background: transparent;
    border: none;
  }
  
  .signature-label {
    font-weight: bold;
    color: #0a3b40;
    margin-bottom: 2px;
    font-size: 8px !important;
  }
  
  /* إخفاء معاينة الصور في الطباعة */
  .preview-images {
    display: none !important;
  }
  
  /* منع تكسير الصفحات داخل العناصر المهمة */
  .header, .goal-section, .images {
    page-break-inside: avoid;
    page-break-after: avoid;
  }
  
  /* إجبار الفصل بعد التقرير */
  .report {
    page-break-after: always;
  }
}

/* تخصيص شريط التمرير */
textarea::-webkit-scrollbar {
  width: 8px;
}

textarea::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 10px;
}

textarea::-webkit-scrollbar-thumb {
  background: #0a3b40;
  border-radius: 10px;
}

textarea::-webkit-scrollbar-thumb:hover {
  background: #0d4a50;
}
</style>
</head>
<body>

<div class="tool">
<h2>أداة إعداد التقارير التعليمية (نموذج تجريبي)</h2>

<div class="form-section">
  <div class="section-title">المعلومات الأساسية</div>
  
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
</div>

<div class="form-section">
  <div class="section-title">تفاصيل التقرير</div>
  
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
</div>

<div class="form-section">
  <div class="section-title">النماذج الجاهزة</div>
  
  <div class="auto-row">
    <button class="auto-btn" onclick="loadSmartText(1)">النص الإثرائي 1</button>
    <button class="auto-btn" onclick="loadSmartText(2)">النص الإثرائي 2</button>
    <button class="auto-btn" onclick="loadSmartText(3)">النص الإثرائي 3</button>
    <button class="auto-btn clear-btn" onclick="clearAllFields()">مسح جميع الحقول</button>
  </div>
  <div class="auto-row">
    <button class="auto-btn" onclick="loadSmartText(4)">النص العلاجي 1</button>
    <button class="auto-btn" onclick="loadSmartText(5)">النص العلاجي 2</button>
  </div>
</div>

<div class="form-section">
  <div class="section-title">محتوى التقرير</div>
  
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
</div>

<div class="form-section">
  <div class="section-title">التحليل والتقييم</div>
  
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
</div>

<div class="form-section">
  <div class="section-title">الملحقات</div>
  
  <label>إرفاق الصور (اختياري - الحد الأقصى: صورتين)</label>
  <div class="input-hint">يمكن إرفاق صورتين كحد أقصى تظهران فعاليات النشاط (الحجم الموصى به: 300×200 بكسل)</div>
  <input type="file" id="imageUpload" multiple accept="image/*" onchange="loadImages(this)" title="يمكن إرفاق صورتين كحد أقصى">
  
  <div class="preview-images" id="previewContainer" style="display: none;">
    <h3>معاينة الصور المرفوعة</h3>
    <div class="image-container" id="previewImages"></div>
  </div>
</div>

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

<!-- قسم التقرير للطباعة - ثابت التنسيق -->
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

<div class="grid4">
  <div class="section motivators"><strong>المحفزات</strong><div id="motivators"></div></div>
  <div class="section strengths"><strong>نقاط القوة</strong><div id="strengths"></div></div>
</div>

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

// دالة للحصول على التاريخ الهجري
async function getHijriDate() {
  try {
    const today = new Date();
    const day = today.getDate();
    const month = today.getMonth() + 1;
    const year = today.getFullYear();
    
    const response = await fetch(`https://api.aladhan.com/v1/gToH?date=${day}-${month}-${year}`);
    
    if (!response.ok) throw new Error('فشل في الحصول على التاريخ الهجري');
    
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

// دالة لتحديث معلومات إدارة التعليم
function updateEduInfo(value) {
  if (!value) return;
  const eduHeader = document.getElementById('eduHeader');
  if (eduHeader) {
    eduHeader.textContent = truncateText(value, 50);
  }
}

// مزامنة البيانات مع التقرير
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

// تحميل النص الذكي
function loadSmartText(textNumber) {
  const textData = smartTextsDatabase[textNumber];
  if (!textData) {
    alert("النص غير متوفر، الرجاء المحاولة مرة أخرى");
    return;
  }
  
  const reportSelect = document.getElementById('reportSelect');
  reportSelect.value = textData.reportType;
  sync('reportTitle', textData.reportType);
  
  document.getElementById('goalInput').value = textData.goal;
  document.getElementById('desc1Input').value = textData.desc1;
  document.getElementById('desc2Input').value = textData.desc2;
  document.getElementById('desc3Input').value = textData.desc3;
  document.getElementById('desc4Input').value = textData.desc4;
  document.getElementById('motivatorsInput').value = textData.motivators;
  document.getElementById('strengthsInput').value = textData.strengths;
  document.getElementById('challengesInput').value = textData.challenges;
  document.getElementById('weaknessesInput').value = textData.weaknesses;
  
  sync('goal', textData.goal);
  sync('desc1', textData.desc1);
  sync('desc2', textData.desc2);
  sync('desc3', textData.desc3);
  sync('desc4', textData.desc4);
  sync('motivators', textData.motivators);
  sync('strengths', textData.strengths);
  sync('challenges', textData.challenges);
  sync('weaknesses', textData.weaknesses);
  
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
  
  document.getElementById('semesterSelect').value = "الفصل الدراسي الأول";
  sync('semester', "الفصل الدراسي الأول");
  
  document.getElementById('teacherInput').value = "أحمد محمد علي";
  document.getElementById('principalInput').value = "خالد بن عبدالله السليم";
  sync('teacherName', "أحمد محمد علي");
  sync('principalName', "خالد بن عبدالله السليم");
  
  alert(`تم تحميل ${textData.reportType} - النص ${textNumber} بنجاح!`);
}

// مسح جميع الحقول
function clearAllFields() {
  if (!confirm("هل أنت متأكد من رغبتك في مسح جميع الحقول؟")) return;
  
  const fieldsToClear = [
    'goalInput', 'desc1Input', 'desc2Input', 'desc3Input', 'desc4Input',
    'motivatorsInput', 'strengthsInput', 'challengesInput', 'weaknessesInput',
    'teacherInput', 'principalInput', 'schoolInput'
  ];
  
  const placeholders = ['المستهدفون', 'العدد', 'مكان التنفيذ', 'الصف', 'المادة'];
  
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
  document.getElementById('reportSelect').selectedIndex = 0;
  sync('reportTitle', '');
  
  document.getElementById('previewContainer').style.display = 'none';
  document.getElementById('previewImages').innerHTML = '';
  document.getElementById('imageUpload').value = '';
}

// تحميل الصور
function loadImages(input) {
  const box = document.getElementById("imagesBox");
  const previewContainer = document.getElementById("previewContainer");
  const previewImages = document.getElementById("previewImages");
  
  box.innerHTML = "";
  previewImages.innerHTML = "";
  
  const files = Array.from(input.files).slice(0, 2);
  
  if (files.length > 2) {
    alert("يمكنك إرفاق صورتين كحد أقصى");
    input.value = '';
    previewContainer.style.display = 'none';
    return;
  }
  
  if (files.length === 0) {
    previewContainer.style.display = 'none';
    return;
  }
  
  previewContainer.style.display = 'block';
  
  files.forEach(file => {
    const reader = new FileReader();
    reader.onload = e => {
      // إضافة الصورة للمعاينة
      const previewImg = document.createElement("img");
      previewImg.className = "preview-img";
      previewImg.src = e.target.result;
      previewImages.appendChild(previewImg);
      
      // إضافة الصورة للتقرير
      const img = document.createElement("img");
      img.src = e.target.result;
      box.appendChild(img);
    };
    reader.readAsDataURL(file);
  });
}

// تهيئة الصفحة
window.onload = async function() {
  document.getElementById('schoolInput').value = "مدرسة الملك عبدالله الثانوية";
  sync('school', "مدرسة الملك عبدالله الثانوية");
  updateEduInfo("الإدارة العامة للتعليم بمنطقة الرياض");
  
  await getHijriDate();
  
  setTimeout(() => {
    loadSmartText(1);
  }, 500);
};
</script>
</body>
</html>