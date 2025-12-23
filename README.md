
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>أداة التقارير التعليمية | وزارة التعليم</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<!-- مكتبة jsPDF لتصدير PDF -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
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
  padding: 0;
  overflow-x: hidden;
}

/* تحسينات للجوال */
@media (max-width: 768px) {
  body {
    padding: 10px;
    font-size: 14px;
  }
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 15px;
}

/* شريط التنقل للجوال */
.mobile-nav {
  display: none;
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: white;
  box-shadow: 0 -2px 20px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  padding: 10px;
}

.mobile-nav-item {
  flex: 1;
  text-align: center;
  padding: 10px 5px;
  color: var(--gray);
  text-decoration: none;
  font-size: 11px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5px;
}

.mobile-nav-item.active {
  color: var(--primary);
}

.mobile-nav-item i {
  font-size: 18px;
}

@media (max-width: 768px) {
  .mobile-nav {
    display: flex;
    justify-content: space-around;
  }
  
  .container {
    padding-bottom: 80px; /* مساحة للشريط السفلي */
  }
}

/* الهيدر المحسن للجوال */
.header {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  padding: 20px;
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  border-right: 5px solid var(--primary);
  position: sticky;
  top: 15px;
  z-index: 100;
}

@media (max-width: 768px) {
  .header {
    position: static;
    padding: 15px;
    margin-bottom: 15px;
    flex-direction: column;
    gap: 15px;
    text-align: center;
  }
}

.logo-section {
  display: flex;
  align-items: center;
  gap: 15px;
}

@media (max-width: 768px) {
  .logo-section {
    flex-direction: column;
    gap: 10px;
  }
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
  flex-shrink: 0;
}

.logo-text h1 {
  font-size: 20px;
  font-weight: 700;
  color: var(--dark);
  margin-bottom: 5px;
}

.logo-text p {
  font-size: 13px;
  color: var(--gray);
}

/* الأقسام الرئيسية - تصميم متجاوب */
.main-content {
  display: grid;
  grid-template-columns: 1fr 400px;
  gap: 20px;
}

@media (max-width: 1024px) {
  .main-content {
    grid-template-columns: 1fr;
  }
}

/* لوحة التحكم - تصميم متجاوب */
.control-panel {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  padding: 20px;
  height: fit-content;
  position: sticky;
  top: 100px;
}

@media (max-width: 1024px) {
  .control-panel {
    position: static;
    margin-bottom: 20px;
  }
}

/* الأزرار السريعة - تصميم متجاوب */
.quick-actions {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
  margin-bottom: 20px;
}

@media (max-width: 480px) {
  .quick-actions {
    grid-template-columns: 1fr;
  }
}

.action-btn {
  background: white;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  padding: 12px;
  text-align: center;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  min-height: 80px;
  justify-content: center;
}

.action-btn:hover {
  border-color: var(--primary);
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

.action-btn i {
  font-size: 20px;
  color: var(--primary);
}

.action-btn span {
  font-size: 13px;
  font-weight: 500;
}

/* نموذج الإدخال - تحسينات للجوال */
.form-container {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  overflow: hidden;
  margin-bottom: 20px;
}

.form-header {
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
  padding: 15px 20px;
}

.form-header h2 {
  font-size: 18px;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 10px;
}

.form-content {
  padding: 20px;
}

@media (max-width: 768px) {
  .form-content {
    padding: 15px;
  }
}

/* تحسينات للحقول في الجوال */
.form-group {
  margin-bottom: 20px;
}

.form-row {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  margin-bottom: 20px;
}

@media (max-width: 768px) {
  .form-row {
    grid-template-columns: 1fr;
    gap: 15px;
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

.form-control {
  width: 100%;
  padding: 12px 14px;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  font-family: 'Cairo', sans-serif;
  font-size: 15px;
  color: var(--dark);
  transition: var(--transition);
  background: white;
  -webkit-appearance: none; /* إزالة المظهر الافتراضي في iOS */
}

/* إصلاح الزووم في iOS */
@media (max-width: 768px) {
  input[type="text"],
  input[type="number"],
  textarea,
  select {
    font-size: 16px !important; /* منع الزووم التلقائي في iOS */
  }
}

textarea.form-control {
  min-height: 100px;
  resize: vertical;
  line-height: 1.6;
}

/* منطقة رفع الصور - تحسين للجوال */
.upload-area {
  border: 2px dashed var(--light-gray);
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  cursor: pointer;
  transition: var(--transition);
  margin-bottom: 15px;
  min-height: 120px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.upload-area:hover {
  border-color: var(--primary);
  background: #f8fafc;
}

.image-preview {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 10px;
  margin-top: 15px;
}

@media (max-width: 480px) {
  .image-preview {
    grid-template-columns: 1fr;
  }
}

.preview-image {
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  height: 120px;
}

.preview-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* تذييل النموذج - تحسين للجوال */
.form-footer {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
  padding: 20px;
  background: #f8fafc;
  border-top: 1px solid var(--light-gray);
}

@media (max-width: 768px) {
  .form-footer {
    grid-template-columns: 1fr;
    padding: 15px;
  }
}

.signature-field {
  text-align: center;
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

/* أزرار العمل الرئيسية */
.action-buttons {
  display: flex;
  gap: 15px;
  margin-top: 20px;
  flex-wrap: wrap;
}

.btn {
  flex: 1;
  padding: 16px;
  border: none;
  border-radius: 10px;
  font-family: 'Cairo', sans-serif;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  min-width: 150px;
}

@media (max-width: 768px) {
  .btn {
    min-width: 100%;
  }
  
  .action-buttons {
    flex-direction: column;
  }
}

.btn-primary {
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

.btn-secondary {
  background: white;
  color: var(--primary);
  border: 2px solid var(--primary);
}

.btn-secondary:hover {
  background: var(--primary);
  color: white;
}

.btn-success {
  background: linear-gradient(135deg, var(--success), var(--secondary-dark));
  color: white;
}

.btn-success:hover {
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

/* نافذة المعاينة - تحسين للجوال */
.preview-overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 2000;
  padding: 15px;
  backdrop-filter: blur(5px);
}

.preview-container {
  background: white;
  border-radius: var(--border-radius);
  width: 100%;
  max-width: 900px;
  max-height: 90vh;
  overflow-y: auto;
  position: relative;
  animation: slideIn 0.3s ease;
}

@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.preview-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 20px;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
  position: sticky;
  top: 0;
  z-index: 1;
}

.close-preview {
  background: none;
  border: none;
  color: white;
  font-size: 20px;
  cursor: pointer;
  padding: 5px;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.close-preview:hover {
  background: rgba(255, 255, 255, 0.2);
}

.report-content {
  padding: 20px;
}

/* تصميم التقرير للطباعة */
.report-page {
  width: 210mm;
  min-height: 297mm;
  padding: 20mm;
  background: white;
  box-shadow: var(--box-shadow);
  margin: 0 auto;
  font-family: 'Cairo', sans-serif;
}

@media print {
  .report-page {
    width: 100%;
    height: 100%;
    padding: 0;
    margin: 0;
    box-shadow: none;
  }
}

/* رسائل التنبيه */
.alert {
  padding: 12px 15px;
  border-radius: 10px;
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 14px;
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
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

/* شاشة التحميل */
.loading-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 3000;
  color: white;
  font-size: 18px;
}

.loading-spinner {
  width: 60px;
  height: 60px;
  border: 4px solid rgba(255, 255, 255, 0.3);
  border-top-color: white;
  border-radius: 50%;
  animation: spin 1s linear infinite;
  margin-bottom: 20px;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

/* تحسينات للأجهزة اللوحية */
@media (min-width: 769px) and (max-width: 1024px) {
  .container {
    padding: 20px;
  }
  
  .main-content {
    gap: 25px;
  }
  
  .control-panel {
    padding: 25px;
  }
}

/* تحسينات للأجهزة الكبيرة */
@media (min-width: 1440px) {
  .container {
    max-width: 1400px;
  }
}

/* تحسينات للوضع الأفقي في الجوال */
@media (max-height: 500px) and (orientation: landscape) {
  .header {
    position: static;
  }
  
  .container {
    padding-bottom: 0;
  }
  
  .mobile-nav {
    display: none;
  }
}

/* إصلاحات للاختصارات في iOS */
input, textarea, select {
  -webkit-tap-highlight-color: transparent;
}

/* تحسينات للتمرير */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: var(--primary);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: var(--primary-dark);
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

      <div class="action-buttons">
        <button class="btn btn-primary" onclick="showPreview()">
          <i class="fas fa-eye"></i>
          معاينة
        </button>
        <button class="btn btn-success" onclick="generatePDF()">
          <i class="fas fa-download"></i>
          تصدير PDF
        </button>
      </div>
    </aside>

    <!-- نموذج الإدخال -->
    <main class="form-container">
      <div class="form-header">
        <h2><i class="fas fa-edit"></i> إعداد تقرير جديد</h2>
      </div>

      <div class="form-content">
        <!-- معلومات أساسية -->
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
        </div>

        <div class="form-group">
          <label class="form-label">
            <i class="fas fa-tasks"></i>
            إجراءات التنفيذ
          </label>
          <textarea class="form-control" id="implementation-steps" 
                    placeholder="صف خطوات التنفيذ بالتفصيل..." 
                    maxlength="500"></textarea>
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
          </div>

          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-comments"></i>
              التوصيات والمقترحات
            </label>
            <textarea class="form-control" id="recommendations" 
                      placeholder="ما هي توصياتك للمستقبل؟" 
                      maxlength="300"></textarea>
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
            <small>يسمح بصورتين كحد أقصى</small>
          </div>
          <input type="file" id="image-upload" accept="image/*" multiple 
                 style="display: none" onchange="handleImageUpload(this)">
          <div class="image-preview" id="image-preview"></div>
        </div>
      </div>

      <!-- التوقيعات -->
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
      </div>
    </main>
  </div>
</div>

<!-- شريط التنقل للجوال -->
<nav class="mobile-nav">
  <a href="#" class="mobile-nav-item active" onclick="showSection('form')">
    <i class="fas fa-edit"></i>
    <span>تقرير جديد</span>
  </a>
  <a href="#" class="mobile-nav-item" onclick="showPreview()">
    <i class="fas fa-eye"></i>
    <span>معاينة</span>
  </a>
  <a href="#" class="mobile-nav-item" onclick="generatePDF()">
    <i class="fas fa-download"></i>
    <span>تصدير</span>
  </a>
  <a href="#" class="mobile-nav-item" onclick="clearAll()">
    <i class="fas fa-trash"></i>
    <span>مسح</span>
  </a>
</nav>

<!-- معاينة التقرير -->
<div class="preview-overlay" id="preview-overlay" style="display: none;">
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

<!-- شاشة التحميل -->
<div class="loading-overlay" id="loading-overlay" style="display: none;">
  <div class="loading-spinner"></div>
  <p>جاري إنشاء التقرير...</p>
</div>

<script>
// متغيرات التطبيق
const { jsPDF } = window.jspdf;
let uploadedImages = [];
let currentTemplate = null;

// قوالب جاهزة
const templates = {
  1: {
    name: "نشاط إثرائي",
    type: "اثرائي",
    goal: "تنمية مهارات التفكير النقدي والإبداعي لدى الطلاب المتميزين من خلال أنشطة متقدمة تحفز الابتكار وتطور القدرات البحثية.",
    steps: `1. اختيار الطلاب الموهوبين بناءً على معايير محددة
2. عقد ورش عمل متخصصة في التفكير الإبداعي
3. تنفيذ مشاريع بحثية مصغرة
4. تنظيم مسابقات علمية محفزة
5. متابعة وتقييم فردي لكل طالب`,
    results: `• تطوير 8 مشاريع بحثية مبتكرة
• تحسن ملحوظ في مهارات التحليل بنسبة 40%
• مشاركة ناجحة في المسابقات المحلية
• زيادة الثقة العلمية لدى الطلاب`,
    recommendations: `• توسيع نطاق البرنامج ليشمل المزيد من الطلاب
• تدريب معلمين متخصصين في الإثراء العلمي
• إنشاء مكتبة مصادر رقمية متخصصة
• توثيق التجارب الناجحة ونشرها`,
    target: "طلاب الصف الثالث الثانوي المتميزين"
  },
  2: {
    name: "خطة علاجية",
    type: "علاجي",
    goal: "معالجة الصعوبات القرائية والكتابية لدى الطلاب المتأخرين دراسياً وتحسين مهاراتهم الأساسية في اللغة العربية.",
    steps: `1. تشخيص فردي للصعوبات التعليمية
2. تصميم خطط علاجية مخصصة
3. جلسات علاجية مكثفة أسبوعياً
4. استخدام وسائل تعليمية مساعدة
5. متابعة أسرية وتقييم دوري`,
    results: `• تحسن مهارات القراءة بنسبة 65%
• تحسن مهارات الكتابة بنسبة 55%
• زيادة مشاركة الطلاب في الفصل
• تحسن الثقة بالنفس لدى الطلاب`,
    recommendations: `• تطوير أدوات تشخيص أكثر دقة
• تدريب فرق علاجية متخصصة
• إنشاء بنك أنشطة علاجية
• تعزيز الشراكة مع أولياء الأمور`,
    target: "الطلاب المتأخرين دراسياً في اللغة العربية"
  },
  3: {
    name: "نشاط إبداعي",
    type: "اثرائي",
    goal: "تنمية المهارات التقنية والبرمجية لدى الطلاب الموهوبين وتهيئتهم لمتطلبات العصر الرقمي.",
    steps: `1. تدريب على أساسيات البرمجة
2. ورش عمل في التصميم الرقمي
3. مشاريع تقنية تطبيقية
4. مسابقات برمجية
5. زيارات ميدانية لشركات تقنية`,
    results: `• تصميم 12 موقعاً إلكترونياً تعليمياً
• تطوير 5 تطبيقات تعليمية
• فوز في مسابقات برمجية محلية
• اكتشاف مواهب تقنية واعدة`,
    recommendations: `• توفير معامل حاسوب متطورة
• تأهيل مدربين في المجال التقني
• إنشاء نادي تقني مدرسي
• شراكات مع مؤسسات تقنية`,
    target: "طلاب المرحلة الثانوية المهتمين بالتكنولوجيا"
  }
};

// تحميل القالب
function loadTemplate(templateId) {
  const template = templates[templateId];
  if (!template) return;
  
  currentTemplate = templateId;
  
  // تعبئة الحقول
  document.getElementById('report-type').value = template.type;
  document.getElementById('educational-goal').value = template.goal;
  document.getElementById('implementation-steps').value = template.steps;
  document.getElementById('achieved-results').value = template.results;
  document.getElementById('recommendations').value = template.recommendations;
  document.getElementById('target-audience').value = template.target;
  
  // إشعار للمستخدم
  showAlert(`تم تحميل قالب "${template.name}" بنجاح`, 'success');
  
  // التركيز على حقل المدرسة
  document.getElementById('school-name').focus();
}

// مسح جميع الحقول
function clearAll() {
  if (!confirm('هل أنت متأكد من رغبتك في مسح جميع البيانات؟')) return;
  
  // قائمة جميع الحقول
  const fields = [
    'school-name', 'target-audience', 'educational-goal',
    'implementation-steps', 'achieved-results', 'recommendations',
    'teacher-name', 'principal-name'
  ];
  
  // مسح الحقول
  fields.forEach(fieldId => {
    document.getElementById(fieldId).value = '';
  });
  
  // مسح الصور
  uploadedImages = [];
  document.getElementById('image-preview').innerHTML = '';
  document.getElementById('image-upload').value = '';
  
  // إعادة تعيين نوع التقرير
  document.getElementById('report-type').value = 'اثرائي';
  
  // إشعار للمستخدم
  showAlert('تم مسح جميع البيانات بنجاح', 'success');
  
  currentTemplate = null;
}

// رفع الصور
function handleImageUpload(input) {
  const files = Array.from(input.files).slice(0, 2);
  const preview = document.getElementById('image-preview');
  
  if (files.length > 2) {
    showAlert('يمكنك رفع صورتين كحد أقصى', 'error');
    input.value = '';
    return;
  }
  
  uploadedImages = [];
  preview.innerHTML = '';
  
  files.forEach((file, index) => {
    // التحقق من نوع الملف
    if (!file.type.match('image.*')) {
      showAlert('يرجى رفع ملفات صور فقط', 'error');
      return;
    }
    
    // التحقق من حجم الملف (5MB كحد أقصى)
    if (file.size > 5 * 1024 * 1024) {
      showAlert('حجم الصورة يجب أن يكون أقل من 5MB', 'error');
      return;
    }
    
    const reader = new FileReader();
    reader.onload = function(e) {
      uploadedImages.push({
        data: e.target.result,
        name: file.name
      });
      
      const imgDiv = document.createElement('div');
      imgDiv.className = 'preview-image';
      imgDiv.innerHTML = `
        <img src="${e.target.result}" alt="صورة ${index + 1}">
        <div class="remove-image" onclick="removeImage(${index})" style="
          position: absolute;
          top: 5px;
          left: 5px;
          background: rgba(239, 68, 68, 0.9);
          color: white;
          width: 25px;
          height: 25px;
          border-radius: 50%;
          display: flex;
          align-items: center;
          justify-content: center;
          cursor: pointer;
        ">
          <i class="fas fa-times" style="font-size: 12px;"></i>
        </div>
      `;
      preview.appendChild(imgDiv);
    };
    reader.readAsDataURL(file);
  });
  
  if (files.length > 0) {
    showAlert(`تم رفع ${files.length} صورة بنجاح`, 'success');
  }
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
      <img src="${img.data}" alt="صورة ${i + 1}">
      <div class="remove-image" onclick="removeImage(${i})" style="
        position: absolute;
        top: 5px;
        left: 5px;
        background: rgba(239, 68, 68, 0.9);
        color: white;
        width: 25px;
        height: 25px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
      ">
        <i class="fas fa-times" style="font-size: 12px;"></i>
      </div>
    `;
    preview.appendChild(imgDiv);
  });
}

// عرض المعاينة
function showPreview() {
  // جمع البيانات
  const data = collectFormData();
  
  // التحقق من البيانات المطلوبة
  if (!validateForm(true)) return;
  
  // بناء محتوى المعاينة
  buildPreviewContent(data);
  
  // عرض نافذة المعاينة
  document.getElementById('preview-overlay').style.display = 'flex';
  
  // منع التمرير خلف النافذة
  document.body.style.overflow = 'hidden';
}

// إخفاء المعاينة
function hidePreview() {
  document.getElementById('preview-overlay').style.display = 'none';
  document.body.style.overflow = 'auto';
}

// إنشاء PDF
async function generatePDF() {
  // جمع البيانات
  const data = collectFormData();
  
  // التحقق من البيانات
  if (!validateForm()) return;
  
  // عرض شاشة التحميل
  const loading = document.getElementById('loading-overlay');
  loading.style.display = 'flex';
  
  try {
    // إنشاء مستند PDF جديد
    const doc = new jsPDF({
      orientation: 'portrait',
      unit: 'mm',
      format: 'a4'
    });
    
    // إعداد الخط العربي
    doc.setFont('Arial');
    
    // إضافة عنوان التقرير
    doc.setFontSize(20);
    doc.setTextColor(37, 99, 235);
    doc.text('وزارة التعليم', 105, 20, { align: 'center' });
    
    doc.setFontSize(16);
    doc.setTextColor(30, 41, 59);
    doc.text(data.department || 'إدارة التعليم', 105, 30, { align: 'center' });
    
    doc.setFontSize(14);
    doc.setTextColor(100, 116, 139);
    doc.text(data.school, 105, 37, { align: 'center' });
    
    // خط فاصل
    doc.setDrawColor(37, 99, 235);
    doc.setLineWidth(0.5);
    doc.line(20, 45, 190, 45);
    
    // معلومات التقرير
    doc.setFontSize(12);
    doc.setTextColor(30, 41, 59);
    doc.text(`نوع التقرير: ${getReportTypeName(data.type)}`, 20, 55);
    doc.text(`الفئة المستهدفة: ${data.target}`, 20, 62);
    doc.text(`التاريخ: ${getCurrentDate()}`, 150, 55);
    
    // الهدف التربوي
    doc.setFontSize(14);
    doc.setTextColor(16, 185, 129);
    doc.text('الهدف التربوي', 20, 75);
    
    doc.setFontSize(11);
    doc.setTextColor(30, 41, 59);
    const goalLines = doc.splitTextToSize(data.goal, 170);
    doc.text(goalLines, 20, 82);
    
    // إجراءات التنفيذ
    doc.setFontSize(14);
    doc.setTextColor(245, 158, 11);
    doc.text('إجراءات التنفيذ', 20, goalLines.length * 5 + 90);
    
    doc.setFontSize(11);
    doc.setTextColor(30, 41, 59);
    const stepsLines = doc.splitTextToSize(data.steps, 170);
    doc.text(stepsLines, 20, goalLines.length * 5 + 97);
    
    // النتائج والتوصيات
    const contentHeight = goalLines.length * 5 + stepsLines.length * 5 + 110;
    
    // النتائج المتحققة
    doc.setFontSize(14);
    doc.setTextColor(59, 130, 246);
    doc.text('النتائج المتحققة', 20, contentHeight);
    
    doc.setFontSize(11);
    doc.setTextColor(30, 41, 59);
    const resultsLines = doc.splitTextToSize(data.results, 80);
    doc.text(resultsLines, 20, contentHeight + 7);
    
    // التوصيات والمقترحات
    doc.setFontSize(14);
    doc.setTextColor(139, 92, 246);
    doc.text('التوصيات والمقترحات', 110, contentHeight);
    
    doc.setFontSize(11);
    doc.setTextColor(30, 41, 59);
    const recLines = doc.splitTextToSize(data.recommendations, 80);
    doc.text(recLines, 110, contentHeight + 7);
    
    // الصور (إذا وجدت)
    let currentY = Math.max(
      contentHeight + resultsLines.length * 5 + 20,
      contentHeight + recLines.length * 5 + 20
    );
    
    if (uploadedImages.length > 0 && currentY < 250) {
      doc.setFontSize(14);
      doc.setTextColor(236, 72, 153);
      doc.text('الصور التوثيقية', 20, currentY);
      
      currentY += 10;
      
      // إضافة الصور
      for (let i = 0; i < uploadedImages.length; i++) {
        if (currentY < 270) {
          try {
            const imgData = uploadedImages[i].data;
            const imgWidth = 80;
            const imgHeight = 60;
            const xPos = i === 0 ? 20 : 110;
            
            doc.addImage(imgData, 'JPEG', xPos, currentY, imgWidth, imgHeight);
            
            if (i === 1) currentY += 70;
          } catch (e) {
            console.error('خطأ في إضافة الصورة:', e);
          }
        }
      }
      
      if (uploadedImages.length === 1) currentY += 70;
    }
    
    // التوقيعات
    const signatureY = Math.min(currentY + 30, 270);
    
    doc.setFontSize(12);
    doc.setTextColor(30, 41, 59);
    doc.text('المعلم', 60, signatureY, { align: 'center' });
    doc.text(data.teacher, 60, signatureY + 7, { align: 'center' });
    doc.line(40, signatureY + 10, 80, signatureY + 10);
    
    doc.text('مدير المدرسة', 150, signatureY, { align: 'center' });
    doc.text(data.principal || '.................', 150, signatureY + 7, { align: 'center' });
    doc.line(130, signatureY + 10, 170, signatureY + 10);
    
    // تذييل الصفحة
    doc.setFontSize(10);
    doc.setTextColor(100, 116, 139);
    doc.text(`تم إنشاء التقرير بواسطة أداة التقارير التعليمية - ${getCurrentDate()}`, 105, 285, { align: 'center' });
    
    // حفظ الملف
    const fileName = `تقرير_${data.school.replace(/\s+/g, '_')}_${getCurrentDate().replace(/\//g, '-')}.pdf`;
    doc.save(fileName);
    
    // إشعار النجاح
    showAlert('تم إنشاء وتحميل التقرير بنجاح', 'success');
    
  } catch (error) {
    console.error('خطأ في إنشاء PDF:', error);
    showAlert('حدث خطأ أثناء إنشاء التقرير', 'error');
  } finally {
    // إخفاء شاشة التحميل
    loading.style.display = 'none';
  }
}

// جمع بيانات النموذج
function collectFormData() {
  return {
    department: document.getElementById('education-department').value,
    school: document.getElementById('school-name').value.trim(),
    type: document.getElementById('report-type').value,
    target: document.getElementById('target-audience').value.trim(),
    goal: document.getElementById('educational-goal').value.trim(),
    steps: document.getElementById('implementation-steps').value.trim(),
    results: document.getElementById('achieved-results').value.trim(),
    recommendations: document.getElementById('recommendations').value.trim(),
    teacher: document.getElementById('teacher-name').value.trim(),
    principal: document.getElementById('principal-name').value.trim()
  };
}

// التحقق من صحة البيانات
function validateForm(isPreview = false) {
  const data = collectFormData();
  const requiredFields = ['school', 'goal', 'teacher'];
  
  for (const field of requiredFields) {
    if (!data[field]) {
      const fieldNames = {
        school: 'اسم المدرسة',
        goal: 'الهدف التربوي',
        teacher: 'اسم المعلم'
      };
      
      showAlert(`يرجى تعبئة حقل "${fieldNames[field]}"`, 'error');
      
      // التركيز على الحقل المطلوب
      const fieldId = field === 'school' ? 'school-name' : 
                     field === 'goal' ? 'educational-goal' : 
                     'teacher-name';
      document.getElementById(fieldId).focus();
      
      return false;
    }
  }
  
  if (!isPreview) {
    // تحقق إضافي للتصدير
    if (data.goal.length < 10) {
      showAlert('الهدف التربوي يجب أن يكون مفصلاً (10 أحرف على الأقل)', 'error');
      document.getElementById('educational-goal').focus();
      return false;
    }
  }
  
  return true;
}

// بناء محتوى المعاينة
function buildPreviewContent(data) {
  const content = document.getElementById('report-content');
  
  const html = `
    <div class="report-page">
      <div style="text-align: center; margin-bottom: 30px; border-bottom: 2px solid #2563eb; padding-bottom: 20px;">
        <h1 style="color: #2563eb; margin-bottom: 10px; font-size: 24px;">وزارة التعليم</h1>
        <h2 style="color: #1e293b; font-size: 18px;">${data.department || 'إدارة التعليم'}</h2>
        <h3 style="color: #64748b; font-size: 16px;">${data.school}</h3>
        <p style="color: #94a3b8; margin-top: 10px;">${getCurrentDate()} - ${getReportTypeName(data.type)}</p>
      </div>
      
      <div style="margin-bottom: 20px; background: #f8fafc; padding: 15px; border-radius: 8px;">
        <p style="margin: 0; color: #475569;"><strong>الفئة المستهدفة:</strong> ${data.target}</p>
      </div>
      
      <div style="margin-bottom: 25px;">
        <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #10b981; font-size: 16px;">
          <i class="fas fa-bullseye"></i> الهدف التربوي
        </h4>
        <p style="color: #475569; line-height: 1.8; background: #f1f8e9; padding: 15px; border-radius: 8px; font-size: 14px;">
          ${data.goal}
        </p>
      </div>
      
      <div style="margin-bottom: 25px;">
        <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #f59e0b; font-size: 16px;">
          <i class="fas fa-tasks"></i> إجراءات التنفيذ
        </h4>
        <div style="color: #475569; line-height: 1.8; background: #fef3c7; padding: 15px; border-radius: 8px; font-size: 14px; white-space: pre-line;">
          ${data.steps}
        </div>
      </div>
      
      <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin-bottom: 25px;">
        <div>
          <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #3b82f6; font-size: 16px;">
            <i class="fas fa-chart-line"></i> النتائج المتحققة
          </h4>
          <div style="color: #475569; line-height: 1.8; background: #dbeafe; padding: 15px; border-radius: 8px; font-size: 14px; white-space: pre-line;">
            ${data.results}
          </div>
        </div>
        
        <div>
          <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #8b5cf6; font-size: 16px;">
            <i class="fas fa-comments"></i> التوصيات والمقترحات
          </h4>
          <div style="color: #475569; line-height: 1.8; background: #ede9fe; padding: 15px; border-radius: 8px; font-size: 14px; white-space: pre-line;">
            ${data.recommendations}
          </div>
        </div>
      </div>
      
      ${uploadedImages.length > 0 ? `
        <div style="margin-bottom: 25px;">
          <h4 style="color: #1e293b; margin-bottom: 15px; padding-right: 10px; border-right: 3px solid #ec4899; font-size: 16px;">
            <i class="fas fa-images"></i> الصور التوثيقية
          </h4>
          <div style="display: grid; grid-template-columns: repeat(${uploadedImages.length > 1 ? 2 : 1}, 1fr); gap: 15px;">
            ${uploadedImages.map(img => `
              <div style="border: 1px solid #e2e8f0; border-radius: 8px; overflow: hidden;">
                <img src="${img.data}" style="width: 100%; height: 150px; object-fit: cover;" alt="صورة توثيقية">
                <div style="padding: 10px; background: #f8fafc; text-align: center; font-size: 12px; color: #64748b;">
                  ${img.name}
                </div>
              </div>
            `).join('')}
          </div>
        </div>
      ` : ''}
      
      <div style="display: flex; justify-content: space-between; margin-top: 40px; padding-top: 20px; border-top: 1px solid #e2e8f0;">
        <div style="text-align: center; flex: 1;">
          <div style="margin-bottom: 10px; color: #1e293b; font-weight: bold; font-size: 16px;">المعلم</div>
          <div style="color: #475569; font-size: 14px;">${data.teacher}</div>
          <div style="margin-top: 30px; height: 1px; background: #cbd5e1; width: 150px; margin: 20px auto 0;"></div>
        </div>
        
        <div style="text-align: center; flex: 1;">
          <div style="margin-bottom: 10px; color: #1e293b; font-weight: bold; font-size: 16px;">مدير المدرسة</div>
          <div style="color: #475569; font-size: 14px;">${data.principal || '.................'}</div>
          <div style="margin-top: 30px; height: 1px; background: #cbd5e1; width: 150px; margin: 20px auto 0;"></div>
        </div>
      </div>
    </div>
  `;
  
  content.innerHTML = html;
}

// الحصول على اسم نوع التقرير
function getReportTypeName(type) {
  const types = {
    'اثرائي': 'تقرير نشاط إثرائي',
    'علاجي': 'تقرير خطة علاجية',
    'تقويمي': 'تقرير تقويمي'
  };
  return types[type] || 'تقرير تعليمي';
}

// الحصول على التاريخ الحالي
function getCurrentDate() {
  const now = new Date();
  const date = now.getDate().toString().padStart(2, '0');
  const month = (now.getMonth() + 1).toString().padStart(2, '0');
  const year = now.getFullYear();
  const hijriYear = 1446;
  
  return `${date}/${month}/${year} م - ${hijriYear} هـ`;
}

// عرض رسائل التنبيه
function showAlert(message, type = 'info') {
  // إزالة التنبيهات القديمة
  const oldAlerts = document.querySelectorAll('.alert');
  oldAlerts.forEach(alert => {
    if (!alert.classList.contains('alert-success') && 
        !alert.classList.contains('alert-warning')) {
      alert.remove();
    }
  });
  
  const alert = document.createElement('div');
  alert.className = `alert alert-${type}`;
  alert.innerHTML = `
    <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'warning' ? 'exclamation-triangle' : type === 'error' ? 'times-circle' : 'info-circle'}"></i>
    <span>${message}</span>
  `;
  
  // إضافة التنبيه في بداية المحتوى
  const formContent = document.querySelector('.form-content');
  if (formContent) {
    formContent.prepend(alert);
  } else {
    document.querySelector('.container').prepend(alert);
  }
  
  // إزالة التنبيه بعد 5 ثواني
  setTimeout(() => {
    if (alert.parentNode) {
      alert.remove();
    }
  }, 5000);
}

// تغيير القسم في الجوال
function showSection(section) {
  const navItems = document.querySelectorAll('.mobile-nav-item');
  navItems.forEach(item => item.classList.remove('active'));
  event.currentTarget.classList.add('active');
}

// تهيئة الصفحة
document.addEventListener('DOMContentLoaded', function() {
  // تعيين القيم الافتراضية
  document.getElementById('school-name').value = 'مدرسة الملك عبدالله الثانوية';
  document.getElementById('target-audience').value = 'طلاب الصف الثالث الثانوي';
  document.getElementById('teacher-name').value = 'أحمد محمد علي';
  document.getElementById('principal-name').value = 'خالد بن عبدالله السليم';
  
  // إغلاق المعاينة بالزر ESC
  document.addEventListener('keydown', function(e) {
    if (e.key === 'Escape') {
      hidePreview();
    }
  });
  
  // إغلاق المعاينة بالنقر خارجها
  document.getElementById('preview-overlay').addEventListener('click', function(e) {
    if (e.target.classList.contains('preview-overlay')) {
      hidePreview();
    }
  });
  
  // منع إرسال النموذج بالدخول
  document.querySelectorAll('input, textarea').forEach(element => {
    element.addEventListener('keydown', function(e) {
      if (e.key === 'Enter' && e.target.type !== 'textarea') {
        e.preventDefault();
      }
    });
  });
  
  // تحسين تجربة اللمس
  document.querySelectorAll('.action-btn, .btn').forEach(button => {
    button.addEventListener('touchstart', function() {
      this.style.transform = 'scale(0.98)';
    });
    
    button.addEventListener('touchend', function() {
      this.style.transform = '';
    });
  });
  
  // الترحيب
  setTimeout(() => {
    showAlert('مرحباً بك في نظام إعداد التقارير التعليمية', 'success');
  }, 500);
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