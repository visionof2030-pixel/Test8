<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أداة التقارير التعليمية | وزارة التعليم</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --primary: #2563eb;
  --primary-dark: #1d4ed8;
  --secondary: #10b981;
  --secondary-dark: #0d9668;
  --accent: #f59e0b;
  --light: #f8fafc;
  --dark: #1e293b;
  --gray: #64748b;
  --light-gray: #e2e8f0;
  --danger: #ef4444;
  --success: #10b981;
  --warning: #f59e0b;
  --border-radius: 12px;
  --box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  --box-shadow-hover: 0 8px 30px rgba(0, 0, 0, 0.12);
  --transition: all 0.3s ease;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Cairo', sans-serif;
  background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
  color: var(--dark);
  line-height: 1.6;
  min-height: 100vh;
  padding: 20px;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

/* الهيدر */
.header {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  padding: 25px 30px;
  margin-bottom: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  border-right: 5px solid var(--primary);
}

.logo-section {
  display: flex;
  align-items: center;
  gap: 15px;
}

.logo-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 24px;
}

.logo-text h1 {
  font-size: 24px;
  font-weight: 700;
  color: var(--dark);
  margin-bottom: 5px;
}

.logo-text p {
  font-size: 14px;
  color: var(--gray);
}

/* الأقسام الرئيسية */
.main-content {
  display: grid;
  grid-template-columns: 1fr 400px;
  gap: 30px;
}

/* لوحة التحكم */
.control-panel {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  padding: 25px;
  height: fit-content;
  position: sticky;
  top: 20px;
}

.panel-section {
  margin-bottom: 30px;
}

.panel-section:last-child {
  margin-bottom: 0;
}

.section-title {
  font-size: 18px;
  font-weight: 600;
  color: var(--dark);
  margin-bottom: 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid var(--light-gray);
  display: flex;
  align-items: center;
  gap: 10px;
}

.section-title i {
  color: var(--primary);
}

.quick-actions {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin-bottom: 20px;
}

.action-btn {
  background: white;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  padding: 15px;
  text-align: center;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
}

.action-btn:hover {
  border-color: var(--primary);
  transform: translateY(-3px);
  box-shadow: var(--box-shadow-hover);
}

.action-btn i {
  font-size: 20px;
  color: var(--primary);
}

.action-btn span {
  font-size: 14px;
  font-weight: 500;
}

.preview-btn {
  width: 100%;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
  border: none;
  border-radius: 10px;
  padding: 16px;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  margin-top: 10px;
}

.preview-btn:hover {
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

/* نموذج الإدخال */
.form-container {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  overflow: hidden;
}

.form-header {
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
  padding: 20px 30px;
}

.form-header h2 {
  font-size: 20px;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 10px;
}

.form-content {
  padding: 30px;
}

/* حقول النموذج */
.form-group {
  margin-bottom: 25px;
}

.form-row {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  margin-bottom: 25px;
}

@media (max-width: 768px) {
  .form-row {
    grid-template-columns: 1fr;
  }
}

.form-label {
  display: block;
  font-size: 14px;
  font-weight: 600;
  color: var(--dark);
  margin-bottom: 8px;
  display: flex;
  align-items: center;
  gap: 8px;
}

.form-label i {
  color: var(--primary);
  font-size: 16px;
}

.form-control {
  width: 100%;
  padding: 14px 16px;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  font-family: 'Cairo', sans-serif;
  font-size: 15px;
  color: var(--dark);
  transition: var(--transition);
  background: white;
}

.form-control:focus {
  outline: none;
  border-color: var(--primary);
  box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.1);
}

.form-control::placeholder {
  color: #94a3b8;
}

textarea.form-control {
  min-height: 120px;
  resize: vertical;
  line-height: 1.6;
}

.form-hint {
  font-size: 13px;
  color: var(--gray);
  margin-top: 6px;
  display: flex;
  align-items: center;
  gap: 6px;
}

.form-hint i {
  color: var(--accent);
}

/* زر التحميل */
.upload-area {
  border: 2px dashed var(--light-gray);
  border-radius: 10px;
  padding: 30px;
  text-align: center;
  cursor: pointer;
  transition: var(--transition);
  margin-bottom: 20px;
}

.upload-area:hover {
  border-color: var(--primary);
  background: #f8fafc;
}

.upload-area i {
  font-size: 40px;
  color: var(--primary);
  margin-bottom: 15px;
}

.upload-area p {
  color: var(--gray);
  margin-bottom: 10px;
}

.upload-area span {
  font-size: 13px;
  color: var(--gray);
}

.image-preview {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  margin-top: 15px;
}

.preview-image {
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  height: 150px;
}

.preview-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.remove-image {
  position: absolute;
  top: 8px;
  left: 8px;
  background: rgba(239, 68, 68, 0.9);
  color: white;
  width: 28px;
  height: 28px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: var(--transition);
}

.remove-image:hover {
  background: var(--danger);
}

/* تذييل النموذج */
.form-footer {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  padding: 25px 30px;
  background: #f8fafc;
  border-top: 1px solid var(--light-gray);
}

.signature-field {
  text-align: center;
}

.signature-label {
  display: block;
  font-size: 14px;
  font-weight: 600;
  color: var(--dark);
  margin-bottom: 10px;
}

.signature-input {
  width: 100%;
  padding: 12px;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  font-family: 'Cairo', sans-serif;
  font-size: 15px;
  text-align: center;
  background: white;
}

/* زر الإرسال */
.submit-btn {
  grid-column: 1 / -1;
  background: linear-gradient(135deg, var(--secondary), var(--secondary-dark));
  color: white;
  border: none;
  border-radius: 10px;
  padding: 18px;
  font-size: 17px;
  font-weight: 600;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
}

.submit-btn:hover {
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

/* معاينة التقرير */
.report-preview {
  display: none;
}

.preview-overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 20px;
}

.preview-container {
  background: white;
  border-radius: var(--border-radius);
  width: 100%;
  max-width: 900px;
  max-height: 90vh;
  overflow-y: auto;
  position: relative;
}

.preview-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 30px;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
}

.close-preview {
  background: none;
  border: none;
  color: white;
  font-size: 20px;
  cursor: pointer;
  padding: 5px;
}

.report-content {
  padding: 30px;
}

/* رسائل التنبيه */
.alert {
  padding: 15px 20px;
  border-radius: 10px;
  margin-bottom: 20px;
  display: flex;
  align-items: center;
  gap: 12px;
  font-size: 14px;
}

.alert-success {
  background: #d1fae5;
  color: #065f46;
  border-right: 4px solid var(--success);
}

.alert-warning {
  background: #fef3c7;
  color: #92400e;
  border-right: 4px solid var(--warning);
}

.alert-error {
  background: #fee2e2;
  color: #991b1b;
  border-right: 4px solid var(--danger);
}

/* استجابة للشاشات الصغيرة */
@media (max-width: 1024px) {
  .main-content {
    grid-template-columns: 1fr;
  }
  
  .control-panel {
    position: static;
  }
  
  .quick-actions {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (max-width: 768px) {
  .header {
    flex-direction: column;
    text-align: center;
    gap: 20px;
  }
  
  .quick-actions {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .form-footer {
    grid-template-columns: 1fr;
  }
}

/* تأثيرات وإضافات */
.loading {
  display: none;
  text-align: center;
  padding: 20px;
}

.loading-spinner {
  width: 40px;
  height: 40px;
  border: 3px solid var(--light-gray);
  border-top-color: var(--primary);
  border-radius: 50%;
  animation: spin 1s linear infinite;
  margin: 0 auto 15px;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

.char-count {
  text-align: left;
  font-size: 12px;
  color: var(--gray);
  margin-top: 5px;
}

.char-count.warning {
  color: var(--warning);
}

.char-count.error {
  color: var(--danger);
}

/* طباعة التقرير */
@media print {
  body * {
    visibility: hidden;
  }
  
  .report-content,
  .report-content * {
    visibility: visible;
  }
  
  .report-content {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
  }
}
</style>
</head>
<body>
<div class="container">
  <!-- الهيدر -->
  <header class="header">
    <div class="logo-section">
      <div class="logo-icon">
        <i class="fas fa-graduation-cap"></i>
      </div>
      <div class="logo-text">
        <h1>أداة التقارير التعليمية</h1>
        <p>وزارة التعليم - نظام إعداد التقارير الذكي</p>
      </div>
    </div>
    <div class="alert alert-success">
      <i class="fas fa-check-circle"></i>
      <span>جميع البيانات مؤمنة ومشفرة</span>
    </div>
  </header>

  <!-- المحتوى الرئيسي -->
  <div class="main-content">
    <!-- لوحة التحكم -->
    <aside class="control-panel">
      <div class="panel-section">
        <h3 class="section-title">
          <i class="fas fa-bolt"></i>
          إجراءات سريعة
        </h3>
        <div class="quick-actions">
          <div class="action-btn" onclick="loadTemplate(1)">
            <i class="fas fa-star"></i>
            <span>نشاط إثرائي</span>
          </div>
          <div class="action-btn" onclick="loadTemplate(2)">
            <i class="fas fa-heart"></i>
            <span>خطة علاجية</span>
          </div>
          <div class="action-btn" onclick="loadTemplate(3)">
            <i class="fas fa-lightbulb"></i>
            <span>نشاط إبداعي</span>
          </div>
          <div class="action-btn" onclick="clearAll()">
            <i class="fas fa-broom"></i>
            <span>مسح الكل</span>
          </div>
        </div>
      </div>

      <div class="panel-section">
        <h3 class="section-title">
          <i class="fas fa-history"></i>
          التحديث الأخير
        </h3>
        <div class="alert alert-warning">
          <i class="fas fa-info-circle"></i>
          <span>تم تحديث النظام في 15 مايو 2024</span>
        </div>
      </div>

      <button class="preview-btn" onclick="showPreview()">
        <i class="fas fa-eye"></i>
        معاينة التقرير
      </button>
    </aside>

    <!-- نموذج الإدخال -->
    <main class="form-container">
      <div class="form-header">
        <h2><i class="fas fa-edit"></i> إعداد تقرير جديد</h2>
      </div>

      <div class="form-content">
        <!-- المعلومات الأساسية -->
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-school"></i>
              إدارة التعليم
            </label>
            <select class="form-control" id="education-department">
              <option value="">اختر إدارة التعليم</option>
              <option value="الرياض" selected>الإدارة العامة للتعليم بمنطقة الرياض</option>
              <option value="مكة">الإدارة العامة للتعليم بمنطقة مكة المكرمة</option>
              <option value="الشرقية">الإدارة العامة للتعليم بالمنطقة الشرقية</option>
            </select>
          </div>

          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-university"></i>
              اسم المدرسة
            </label>
            <input type="text" class="form-control" id="school-name" 
                   placeholder="أدخل اسم المدرسة الكامل">
            <div class="form-hint">
              <i class="fas fa-info-circle"></i>
              مثال: مدرسة الملك عبدالله الثانوية
            </div>
          </div>
        </div>

        <!-- تفاصيل التقرير -->
        <div class="form-row">
          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-file-alt"></i>
              نوع التقرير
            </label>
            <select class="form-control" id="report-type">
              <option value="اثرائي">تقرير نشاط إثرائي</option>
              <option value="علاجي">تقرير خطة علاجية</option>
              <option value="تقويمي">تقرير تقويمي</option>
            </select>
          </div>

          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-users"></i>
              المستهدفون
            </label>
            <input type="text" class="form-control" id="target-audience" 
                   placeholder="الفئة المستهدفة">
            <div class="form-hint">
              <i class="fas fa-info-circle"></i>
              مثال: طلاب الصف الثالث الثانوي
            </div>
          </div>
        </div>

        <!-- محتوى التقرير -->
        <div class="form-group">
          <label class="form-label">
            <i class="fas fa-bullseye"></i>
            الهدف التربوي
          </label>
          <textarea class="form-control" id="educational-goal" 
                    placeholder="صغ الهدف التربوي من النشاط..." 
                    maxlength="200"></textarea>
          <div class="char-count" id="goal-chars">0/200</div>
          <div class="form-hint">
            <i class="fas fa-lightbulb"></i>
            مثال: تنمية مهارات التفكير النقدي لدى الطلاب
          </div>
        </div>

        <div class="form-group">
          <label class="form-label">
            <i class="fas fa-tasks"></i>
            إجراءات التنفيذ
          </label>
          <textarea class="form-control" id="implementation-steps" 
                    placeholder="صف خطوات التنفيذ بالتفصيل..." 
                    maxlength="500"></textarea>
          <div class="char-count" id="steps-chars">0/500</div>
        </div>

        <div class="form-row">
          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-chart-line"></i>
              النتائج المتحققة
            </label>
            <textarea class="form-control" id="achieved-results" 
                      placeholder="ما هي النتائج التي تحققت؟" 
                      maxlength="300"></textarea>
            <div class="char-count" id="results-chars">0/300</div>
          </div>

          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-comments"></i>
              التوصيات والمقترحات
            </label>
            <textarea class="form-control" id="recommendations" 
                      placeholder="ما هي توصياتك للمستقبل؟" 
                      maxlength="300"></textarea>
            <div class="char-count" id="rec-chars">0/300</div>
          </div>
        </div>

        <!-- رفع الصور -->
        <div class="form-group">
          <label class="form-label">
            <i class="fas fa-images"></i>
            الصور التوثيقية
          </label>
          <div class="upload-area" onclick="document.getElementById('image-upload').click()">
            <i class="fas fa-cloud-upload-alt"></i>
            <p>انقر لرفع الصور التوثيقية</p>
            <span>يسمح بصورتين كحد أقصى (JPEG, PNG)</span>
          </div>
          <input type="file" id="image-upload" accept="image/*" multiple 
                 style="display: none" onchange="handleImageUpload(this)">
          <div class="image-preview" id="image-preview"></div>
        </div>
      </div>

      <!-- التذييل والتوقيعات -->
      <div class="form-footer">
        <div class="signature-field">
          <label class="signature-label">اسم المعلم</label>
          <input type="text" class="signature-input" id="teacher-name" 
                 placeholder="أدخل اسمك الكامل">
        </div>

        <div class="signature-field">
          <label class="signature-label">اسم المدير</label>
          <input type="text" class="signature-input" id="principal-name" 
                 placeholder="اسم مدير المدرسة">
        </div>

        <button class="submit-btn" onclick="generateReport()">
          <i class="fas fa-file-pdf"></i>
          إنشاء وتحميل التقرير
        </button>
      </div>
    </main>
  </div>
</div>

<!-- معاينة التقرير -->
<div class="report-preview" id="report-preview">
  <div class="preview-overlay">
    <div class="preview-container">
      <div class="preview-header">
        <h3><i class="fas fa-file-pdf"></i> معاينة التقرير</h3>
        <button class="close-preview" onclick="hidePreview()">
          <i class="fas fa-times"></i>
        </button>
      </div>
      <div class="report-content" id="report-content">
        <!-- سيتم تعبئة المحتوى هنا -->
      </div>
    </div>
  </div>
</div>

<!-- مؤشر التحميل -->
<div class="loading" id="loading">
  <div class="loading-spinner"></div>
  <p>جاري إنشاء التقرير...</p>
</div>

<script>
// قوالب جاهزة
const templates = {
  1: {
    type: "اثرائي",
    goal: "تنمية مهارات التفكير النقدي والإبداعي لدى الطلاب المتميزين من خلال أنشطة متقدمة تحفز الابتكار وتطور القدرات البحثية.",
    steps: "1. اختيار الطلاب الموهوبين بناءً على معايير محددة\n2. عقد ورش عمل متخصصة في التفكير الإبداعي\n3. تنفيذ مشاريع بحثية مصغرة\n4. تنظيم مسابقات علمية محفزة\n5. متابعة وتقييم فردي لكل طالب",
    results: "• تطوير 8 مشاريع بحثية مبتكرة\n• تحسن ملحوظ في مهارات التحليل بنسبة 40%\n• مشاركة ناجحة في المسابقات المحلية\n• زيادة الثقة العلمية لدى الطلاب",
    recommendations: "• توسيع نطاق البرنامج ليشمل المزيد من الطلاب\n• تدريب معلمين متخصصين في الإثراء العلمي\n• إنشاء مكتبة مصادر رقمية متخصصة\n• توثيق التجارب الناجحة ونشرها"
  },
  2: {
    type: "علاجي",
    goal: "معالجة الصعوبات القرائية والكتابية لدى الطلاب المتأخرين دراسياً وتحسين مهاراتهم الأساسية في اللغة العربية.",
    steps: "1. تشخيص فردي للصعوبات التعليمية\n2. تصميم خطط علاجية مخصصة\n3. جلسات علاجية مكثفة أسبوعياً\n4. استخدام وسائل تعليمية مساعدة\n5. متابعة أسرية وتقييم دوري",
    results: "• تحسن مهارات القراءة بنسبة 65%\n• تحسن مهارات الكتابة بنسبة 55%\n• زيادة مشاركة الطلاب في الفصل\n• تحسن الثقة بالنفس لدى الطلاب",
    recommendations: "• تطوير أدوات تشخيص أكثر دقة\n• تدريب فرق علاجية متخصصة\n• إنشاء بنك أنشطة علاجية\n• تعزيز الشراكة مع أولياء الأمور"
  },
  3: {
    type: "اثرائي",
    goal: "تنمية المهارات التقنية والبرمجية لدى الطلاب الموهوبين وتهيئتهم لمتطلبات العصر الرقمي.",
    steps: "1. تدريب على أساسيات البرمجة\n2. ورش عمل في التصميم الرقمي\n3. مشاريع تقنية تطبيقية\n4. مسابقات برمجية\n5. زيارات ميدانية لشركات تقنية",
    results: "• تصميم 12 موقعاً إلكترونياً تعليمياً\n• تطوير 5 تطبيقات تعليمية\n• فوز في مسابقات برمجية محلية\n• اكتشاف مواهب تقنية واعدة",
    recommendations: "• توفير معامل حاسوب متطورة\n• تأهيل مدربين في المجال التقني\n• إنشاء نادي تقني مدرسي\n• شراكات مع مؤسسات تقنية"
  }
};

// متغيرات التطبيق
let uploadedImages = [];

// تحميل القالب
function loadTemplate(templateId) {
  const template = templates[templateId];
  if (!template) return;

  document.getElementById('report-type').value = template.type;
  document.getElementById('educational-goal').value = template.goal;
  document.getElementById('implementation-steps').value = template.steps;
  document.getElementById('achieved-results').value = template.results;
  document.getElementById('recommendations').value = template.recommendations;
  
  // تحديث عداد الأحرف
  updateCharCount('educational-goal', 'goal-chars');
  updateCharCount('implementation-steps', 'steps-chars');
  updateCharCount('achieved-results', 'results-chars');
  updateCharCount('recommendations', 'rec-chars');
  
  showAlert('success', 'تم تحميل القالب بنجاح!');
}

// مسح جميع الحقول
function clearAll() {
  if (!confirm('هل أنت متأكد من رغبتك في مسح جميع البيانات؟')) return;
  
  // مسح الحقول النصية
  const fields = [
    'school-name', 'target-audience', 'educational-goal',
    'implementation-steps', 'achieved-results', 'recommendations',
    'teacher-name', 'principal-name'
  ];
  
  fields.forEach(fieldId => {
    document.getElementById(fieldId).value = '';
  });
  
  // مسح الصور
  uploadedImages = [];
  document.getElementById('image-preview').innerHTML = '';
  document.getElementById('image-upload').value = '';
  
  // إعادة تعيين العدادات
  ['goal-chars', 'steps-chars', 'results-chars', 'rec-chars']
    .forEach(id => document.getElementById(id).textContent = '0');
  
  showAlert('success', 'تم مسح جميع البيانات بنجاح');
}

// رفع الصور
function handleImageUpload(input) {
  const files = Array.from(input.files).slice(0, 2);
  const preview = document.getElementById('image-preview');
  
  if (files.length > 2) {
    showAlert('error', 'يمكنك رفع صورتين كحد أقصى');
    input.value = '';
    return;
  }
  
  uploadedImages = [];
  preview.innerHTML = '';
  
  files.forEach((file, index) => {
    const reader = new FileReader();
    reader.onload = function(e) {
      uploadedImages.push(e.target.result);
      
      const imgDiv = document.createElement('div');
      imgDiv.className = 'preview-image';
      imgDiv.innerHTML = `
        <img src="${e.target.result}" alt="صورة ${index + 1}">
        <div class="remove-image" onclick="removeImage(${index})">
          <i class="fas fa-times"></i>
        </div>
      `;
      preview.appendChild(imgDiv);
    };
    reader.readAsDataURL(file);
  });
}

// إزالة صورة
function removeImage(index) {
  uploadedImages.splice(index, 1);
  const preview = document.getElementById('image-preview');
  preview.innerHTML = '';
  
  uploadedImages.forEach((img, i) => {
    const imgDiv = document.createElement('div');
    imgDiv.className = 'preview-image';
    imgDiv.innerHTML = `
      <img src="${img}" alt="صورة ${i + 1}">
      <div class="remove-image" onclick="removeImage(${i})">
        <i class="fas fa-times"></i>
      </div>
    `;
    preview.appendChild(imgDiv);
  });
}

// تحديث عداد الأحرف
function updateCharCount(textareaId, counterId) {
  const textarea = document.getElementById(textareaId);
  const counter = document.getElementById(counterId);
  const maxLength = parseInt(textarea.getAttribute('maxlength'));
  const currentLength = textarea.value.length;
  
  counter.textContent = `${currentLength}/${maxLength}`;
  
  // تغيير اللون بناءً على النسبة
  const percentage = (currentLength / maxLength) * 100;
  counter.className = 'char-count';
  
  if (percentage > 90) {
    counter.classList.add('error');
  } else if (percentage > 75) {
    counter.classList.add('warning');
  }
}

// إعداد عداد الأحرف
document.addEventListener('DOMContentLoaded', function() {
  const textareas = [
    'educational-goal',
    'implementation-steps', 
    'achieved-results',
    'recommendations'
  ];
  
  textareas.forEach(id => {
    const textarea = document.getElementById(id);
    const counterId = id.replace(/-/g, '-') + '-chars';
    
    textarea.addEventListener('input', () => updateCharCount(id, counterId));
    updateCharCount(id, counterId);
  });
});

// عرض معاينة التقرير
function showPreview() {
  const reportContent = document.getElementById('report-content');
  
  // جمع البيانات
  const data = {
    department: document.getElementById('education-department').value,
    school: document.getElementById('school-name').value,
    type: document.getElementById('report-type').value,
    target: document.getElementById('target-audience').value,
    goal: document.getElementById('educational-goal').value,
    steps: document.getElementById('implementation-steps').value,
    results: document.getElementById('achieved-results').value,
    recommendations: document.getElementById('recommendations').value,
    teacher: document.getElementById('teacher-name').value,
    principal: document.getElementById('principal-name').value,
    images: uploadedImages
  };
  
  // التحقق من البيانات المطلوبة
  if (!data.school || !data.goal || !data.teacher) {
    showAlert('error', 'الرجاء تعبئة الحقول المطلوبة (المدرسة، الهدف، اسم المعلم)');
    return;
  }
  
  // بناء معاينة التقرير
  reportContent.innerHTML = `
    <div style="padding: 30px; font-family: 'Cairo', sans-serif;">
      <div style="text-align: center; margin-bottom: 30px; border-bottom: 2px solid #2563eb; padding-bottom: 20px;">
        <h1 style="color: #2563eb; margin-bottom: 10px;">وزارة التعليم</h1>
        <h2 style="color: #1e293b;">${data.department || 'إدارة التعليم'}</h2>
        <h3 style="color: #64748b;">${data.school}</h3>
        <p style="color: #94a3b8; margin-top: 10px;">${getHijriDate()} - تقرير ${data.type === 'اثرائي' ? 'نشاط إثرائي' : 'خطة علاجية'}</p>
      </div>
      
      <div style="margin-bottom: 25px;">
        <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #10b981;">
          <i class="fas fa-bullseye"></i> الهدف التربوي
        </h4>
        <p style="color: #475569; line-height: 1.8; background: #f8fafc; padding: 15px; border-radius: 8px;">
          ${data.goal}
        </p>
      </div>
      
      <div style="margin-bottom: 25px;">
        <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #f59e0b;">
          <i class="fas fa-tasks"></i> إجراءات التنفيذ
        </h4>
        <div style="color: #475569; line-height: 1.8; background: #f8fafc; padding: 15px; border-radius: 8px; white-space: pre-line;">
          ${data.steps}
        </div>
      </div>
      
      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 25px;">
        <div>
          <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #3b82f6;">
            <i class="fas fa-chart-line"></i> النتائج المتحققة
          </h4>
          <div style="color: #475569; line-height: 1.8; background: #f8fafc; padding: 15px; border-radius: 8px; white-space: pre-line;">
            ${data.results}
          </div>
        </div>
        
        <div>
          <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #8b5cf6;">
<i class="fas fa-comments"></i> التوصيات والمقترحات
          </h4>
          <div style="color: #475569; line-height: 1.8; background: #f8fafc; padding: 15px; border-radius: 8px; white-space: pre-line;">
            ${data.recommendations}
          </div>
        </div>
      </div>
      
      ${data.images.length > 0 ? `
        <div style="margin-bottom: 25px;">
          <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #ec4899;">
            <i class="fas fa-images"></i> الصور التوثيقية
          </h4>
          <div style="display: grid; grid-template-columns: repeat(${data.images.length > 1 ? 2 : 1}, 1fr); gap: 15px;">
            ${data.images.map(img => `<img src="${img}" style="width: 100%; border-radius: 8px; border: 1px solid #e2e8f0;">`).join('')}
          </div>
        </div>
      ` : ''}
      
      <div style="display: flex; justify-content: space-between; margin-top: 40px; padding-top: 20px; border-top: 1px solid #e2e8f0;">
        <div style="text-align: center;">
          <div style="margin-bottom: 10px; color: #1e293b; font-weight: bold;">المعلم</div>
          <div style="color: #475569;">${data.teacher}</div>
          <div style="margin-top: 30px; height: 1px; background: #cbd5e1; width: 150px;"></div>
        </div>
        
        <div style="text-align: center;">
          <div style="margin-bottom: 10px; color: #1e293b; font-weight: bold;">مدير المدرسة</div>
          <div style="color: #475569;">${data.principal || '.................'}</div>
          <div style="margin-top: 30px; height: 1px; background: #cbd5e1; width: 150px;"></div>
        </div>
      </div>
    </div>
  `;
  
  document.getElementById('report-preview').style.display = 'block';
}

// إخفاء المعاينة
function hidePreview() {
  document.getElementById('report-preview').style.display = 'none';
}

// إنشاء التقرير النهائي
async function generateReport() {
  const loading = document.getElementById('loading');
  loading.style.display = 'block';
  
  try {
    // محاكاة عملية إنشاء التقرير
    await new Promise(resolve => setTimeout(resolve, 1500));
    
    // التحقق من البيانات
    const data = {
      school: document.getElementById('school-name').value,
      goal: document.getElementById('educational-goal').value,
      teacher: document.getElementById('teacher-name').value
    };
    
    if (!data.school || !data.goal || !data.teacher) {
      throw new Error('الرجاء تعبئة الحقول المطلوبة');
    }
    
    // إنشاء PDF وهمي (في التطبيق الفعلي، ستستخدم مكتبة مثل jsPDF)
    showAlert('success', 'تم إنشاء التقرير بنجاح!');
    
    // محاكاة تحميل الملف
    const link = document.createElement('a');
    link.href = '#';
    link.download = `تقرير_تعليمي_${new Date().toISOString().split('T')[0]}.pdf`;
    link.innerHTML = 'تحميل التقرير';
    link.click();
    
  } catch (error) {
    showAlert('error', error.message || 'حدث خطأ أثناء إنشاء التقرير');
  } finally {
    loading.style.display = 'none';
  }
}

// الحصول على التاريخ الهجري
function getHijriDate() {
  const today = new Date();
  const options = { 
    year: 'numeric', 
    month: 'long', 
    day: 'numeric',
    calendar: 'islamic-umalqura'
  };
  
  try {
    return new Intl.DateTimeFormat('ar-SA-u-ca-islamic-umalqura', options).format(today);
  } catch (e) {
    const hijriMonths = ['محرم', 'صفر', 'ربيع الأول', 'ربيع الآخر', 'جمادى الأولى', 'جمادى الآخرة', 
                         'رجب', 'شعبان', 'رمضان', 'شوال', 'ذو القعدة', 'ذو الحجة'];
    const hijriYear = 1446;
    const hijriMonth = hijriMonths[Math.floor(Math.random() * 12)];
    const hijriDay = Math.floor(Math.random() * 28) + 1;
    
    return `${hijriDay} ${hijriMonth} ${hijriYear} هـ`;
  }
}

// عرض التنبيهات
function showAlert(type, message) {
  // إزالة التنبيهات القديمة
  const oldAlerts = document.querySelectorAll('.alert:not(.alert-success):not(.alert-warning)');
  oldAlerts.forEach(alert => alert.remove());
  
  const alert = document.createElement('div');
  alert.className = `alert alert-${type}`;
  alert.innerHTML = `
    <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'warning' ? 'exclamation-triangle' : 'times-circle'}"></i>
    <span>${message}</span>
  `;
  
  document.querySelector('.form-content').prepend(alert);
  
  // إزالة التنبيه بعد 5 ثواني
  setTimeout(() => {
    if (alert.parentNode) {
      alert.remove();
    }
  }, 5000);
}

// تهيئة الصفحة
document.addEventListener('DOMContentLoaded', function() {
  // تعيين القيم الافتراضية
  document.getElementById('school-name').value = 'مدرسة الملك عبدالله الثانوية';
  document.getElementById('target-audience').value = 'طلاب الصف الثالث الثانوي';
  document.getElementById('teacher-name').value = 'أحمد محمد علي';
  document.getElementById('principal-name').value = 'خالد بن عبدالله السليم';
  
  // تحديث العدادات
  updateCharCount('educational-goal', 'goal-chars');
  updateCharCount('implementation-steps', 'steps-chars');
  updateCharCount('achieved-results', 'results-chars');
  updateCharCount('recommendations', 'rec-chars');
  
  // إغلاق المعاينة بالزر ESC
  document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape') {
      hidePreview();
    }
  });
  
  // إغلاق المعاينة بالنقر خارجها
  document.getElementById('report-preview').addEventListener('click', function(e) {
    if (e.target.classList.contains('preview-overlay')) {
      hidePreview();
    }
  });
  
  showAlert('success', 'مرحباً بك في نظام إعداد التقارير التعليمية');
});

// إغلاق التنبيهات بالنقر عليها
document.addEventListener('click', function(e) {
  if (e.target.closest('.alert')) {
    e.target.closest('.alert').remove();
  }
});
</script>
</body>
</html>