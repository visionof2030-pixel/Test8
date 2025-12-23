<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>أداة التقارير التعليمية | وزارة التعليم</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --primary: #1a56db;
  --primary-dark: #1e40af;
  --secondary: #059669;
  --secondary-dark: #047857;
  --accent: #d97706;
  --light: #f8fafc;
  --dark: #1f2937;
  --gray: #6b7280;
  --light-gray: #e5e7eb;
  --danger: #dc2626;
  --success: #059669;
  --warning: #d97706;
  --border-radius: 12px;
  --box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  --box-shadow-hover: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  --transition: all 0.2s ease;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
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

/* تحسينات للأجهزة المحمولة */
@media (max-width: 768px) {
  body {
    font-size: 15px;
    -webkit-text-size-adjust: 100%;
  }
}

.container {
  max-width: 100%;
  margin: 0 auto;
  padding: 15px;
}

/* الهيدر متجاوب */
.header {
  background: white;
  border-radius: var(--border-radius);
  box-shadow: var(--box-shadow);
  padding: 15px;
  margin-bottom: 15px;
  display: flex;
  flex-direction: column;
  gap: 15px;
  border-right: 4px solid var(--primary);
}

.header-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 10px;
}

.header-bottom {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

@media (max-width: 480px) {
  .header-top {
    flex-direction: column;
    text-align: center;
  }
  
  .header-bottom {
    flex-direction: column;
  }
}

.logo-section {
  display: flex;
  align-items: center;
  gap: 12px;
}

.logo-icon {
  width: 45px;
  height: 45px;
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 22px;
  flex-shrink: 0;
}

.logo-text h1 {
  font-size: 18px;
  font-weight: 700;
  color: var(--dark);
  margin-bottom: 3px;
  line-height: 1.3;
}

.logo-text p {
  font-size: 13px;
  color: var(--gray);
  line-height: 1.4;
}

/* زر القائمة للجوال */
.mobile-menu-btn {
  display: none;
  background: none;
  border: none;
  color: var(--primary);
  font-size: 24px;
  cursor: pointer;
  padding: 5px;
}

@media (max-width: 768px) {
  .mobile-menu-btn {
    display: block;
  }
}

/* شريط التنقل السفلي للجوال */
.mobile-nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: white;
  box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
  z-index: 1000;
  padding: 10px 5px;
  display: none;
  justify-content: space-around;
  backdrop-filter: blur(10px);
}

@media (max-width: 768px) {
  .mobile-nav {
    display: flex;
  }
  
  .container {
    padding-bottom: 80px;
  }
}

.nav-btn {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  background: none;
  border: none;
  color: var(--gray);
  font-size: 11px;
  padding: 6px 4px;
  cursor: pointer;
  flex: 1;
  min-width: 0;
  transition: var(--transition);
}

.nav-btn.active {
  color: var(--primary);
}

.nav-btn i {
  font-size: 16px;
}

.nav-btn:hover {
  transform: translateY(-2px);
}

/* المحتوى الرئيسي */
.main-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 15px;
}

@media (min-width: 1024px) {
  .main-content {
    grid-template-columns: 1fr 350px;
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
  top: 15px;
}

@media (max-width: 1024px) {
  .control-panel {
    position: static;
    order: 2;
  }
}

/* القوالب السريعة */
.quick-templates {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 10px;
  margin-bottom: 20px;
}

@media (max-width: 480px) {
  .quick-templates {
    grid-template-columns: 1fr;
  }
}

.template-btn {
  background: white;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  padding: 12px;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  text-align: center;
  min-height: 90px;
  justify-content: center;
}

.template-btn:hover {
  border-color: var(--primary);
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

.template-btn i {
  font-size: 20px;
  color: var(--primary);
}

.template-btn span {
  font-size: 13px;
  font-weight: 500;
}

/* أزرار العمل */
.action-buttons {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 20px;
}

.action-btn {
  padding: 14px;
  border: none;
  border-radius: 10px;
  font-family: 'Cairo', sans-serif;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  transition: var(--transition);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.action-btn-primary {
  background: linear-gradient(135deg, var(--primary), var(--primary-dark));
  color: white;
}

.action-btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: var(--box-shadow-hover);
}

.action-btn-secondary {
  background: white;
  color: var(--primary);
  border: 2px solid var(--primary);
}

.action-btn-secondary:hover {
  background: var(--primary);
  color: white;
}

.action-btn-success {
  background: linear-gradient(135deg, var(--success), var(--secondary-dark));
  color: white;
}

.action-btn-success:hover {
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

/* تحسينات للحقول في الجوال */
.form-section {
  margin-bottom: 25px;
}

.form-section-title {
  font-size: 16px;
  font-weight: 600;
  color: var(--dark);
  margin-bottom: 15px;
  padding-bottom: 8px;
  border-bottom: 2px solid var(--light-gray);
  display: flex;
  align-items: center;
  gap: 8px;
}

.form-section-title i {
  color: var(--primary);
}

.form-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 15px;
}

@media (max-width: 768px) {
  .form-grid {
    grid-template-columns: 1fr;
  }
}

.form-group {
  margin-bottom: 15px;
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
  padding: 12px 14px;
  border: 2px solid var(--light-gray);
  border-radius: 10px;
  font-family: 'Cairo', sans-serif;
  font-size: 15px;
  color: var(--dark);
  transition: var(--transition);
  background: white;
  -webkit-appearance: none;
}

/* إصلاح الزووم في iOS */
@media (max-width: 768px) {
  input[type="text"],
  input[type="number"],
  textarea,
  select {
    font-size: 16px !important;
  }
}

.form-control:focus {
  outline: none;
  border-color: var(--primary);
  box-shadow: 0 0 0 3px rgba(26, 86, 219, 0.1);
}

.form-control::placeholder {
  color: #9ca3af;
}

textarea.form-control {
  min-height: 100px;
  resize: vertical;
  line-height: 1.6;
}

/* منطقة رفع الصور */
.upload-area {
  border: 2px dashed var(--light-gray);
  border-radius: 10px;
  padding: 20px;
  text-align: center;
  cursor: pointer;
  transition: var(--transition);
  margin-bottom: 15px;
  background: #f9fafb;
}

.upload-area:hover {
  border-color: var(--primary);
  background: #f3f4f6;
}

.upload-area i {
  font-size: 40px;
  color: var(--primary);
  margin-bottom: 10px;
}

.upload-area p {
  color: var(--gray);
  margin-bottom: 5px;
}

.upload-area small {
  font-size: 12px;
  color: var(--gray);
}

.image-preview {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 10px;
  margin-top: 15px;
}

.preview-image {
  position: relative;
  border-radius: 8px;
  overflow: hidden;
  height: 120px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.preview-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.remove-image {
  position: absolute;
  top: 5px;
  left: 5px;
  background: rgba(220, 38, 38, 0.9);
  color: white;
  width: 26px;
  height: 26px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: var(--transition);
  font-size: 12px;
}

.remove-image:hover {
  background: var(--danger);
}

/* التوقيعات */
.signatures-section {
  background: #f9fafb;
  border-radius: 10px;
  padding: 20px;
  margin-top: 20px;
}

.signatures-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

@media (max-width: 480px) {
  .signatures-grid {
    grid-template-columns: 1fr;
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
  margin-top: 8px;
}

/* نافذة المعاينة */
.preview-overlay {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.9);
  display: none;
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
  max-width: 800px;
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
  width: 36px;
  height: 36px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.close-preview:hover {
  background: rgba(255, 255, 255, 0.2);
}

/* تصميم التقرير للطباعة */
.report-content {
  padding: 20px;
  font-family: 'Cairo', sans-serif;
}

.report-header {
  text-align: center;
  margin-bottom: 30px;
  padding-bottom: 20px;
  border-bottom: 3px solid var(--primary);
}

.report-header h1 {
  color: var(--primary);
  font-size: 24px;
  margin-bottom: 10px;
}

.report-header h2 {
  color: var(--dark);
  font-size: 18px;
  margin-bottom: 5px;
}

.report-header h3 {
  color: var(--gray);
  font-size: 16px;
  margin-bottom: 10px;
}

.report-date {
  color: var(--gray);
  font-size: 14px;
}

.report-section {
  margin-bottom: 25px;
}

.report-section-title {
  color: var(--dark);
  font-size: 18px;
  margin-bottom: 15px;
  padding-right: 10px;
  border-right: 3px solid var(--primary);
  display: flex;
  align-items: center;
  gap: 8px;
}

.report-section-content {
  color: var(--dark);
  line-height: 1.8;
  background: #f9fafb;
  padding: 15px;
  border-radius: 8px;
  white-space: pre-line;
}

.report-images {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
  margin-top: 15px;
}

.report-image {
  border: 1px solid var(--light-gray);
  border-radius: 8px;
  overflow: hidden;
}

.report-image img {
  width: 100%;
  height: 150px;
  object-fit: cover;
}

.report-signatures {
  display: flex;
  justify-content: space-between;
  margin-top: 40px;
  padding-top: 20px;
  border-top: 1px solid var(--light-gray);
  flex-wrap: wrap;
  gap: 20px;
}

@media (max-width: 768px) {
  .report-signatures {
    flex-direction: column;
    align-items: center;
  }
}

.signature-box {
  text-align: center;
  flex: 1;
  min-width: 200px;
}

.signature-name {
  font-size: 16px;
  font-weight: 600;
  color: var(--dark);
  margin-top: 15px;
}

.signature-line {
  width: 150px;
  height: 1px;
  background: var(--light-gray);
  margin: 10px auto;
}

/* رسائل التنبيه */
.alert {
  padding: 12px 15px;
  border-radius: 8px;
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 14px;
  animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-10px); }
  to { opacity: 1; transform: translateY(0); }
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

.alert-info {
  background: #dbeafe;
  color: #1e40af;
  border-right: 4px solid var(--primary);
}

/* شاشة التحميل */
.loading-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.9);
  display: none;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 3000;
  color: white;
  font-size: 18px;
  text-align: center;
  padding: 20px;
}

.loading-spinner {
  width: 50px;
  height: 50px;
  border: 3px solid rgba(255, 255, 255, 0.3);
  border-top-color: white;
  border-radius: 50%;
  animation: spin 1s linear infinite;
  margin-bottom: 20px;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}

/* تحسينات للتمرير */
::-webkit-scrollbar {
  width: 8px;
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

/* طباعة التقرير */
@media print {
  body * {
    visibility: hidden;
  }
  
  .preview-container,
  .preview-container * {
    visibility: visible;
  }
  
  .preview-container {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    max-width: 100%;
    box-shadow: none;
    border-radius: 0;
  }
  
  .preview-header {
    display: none;
  }
  
  .report-content {
    padding: 0;
  }
  
  .action-buttons,
  .mobile-nav,
  .header {
    display: none !important;
  }
}

/* تحسينات للوضع الأفقي */
@media (max-height: 500px) and (orientation: landscape) {
  .mobile-nav {
    display: none;
  }
  
  .container {
    padding-bottom: 20px;
  }
}
</style>
</head>
<body>
<div class="container">
  <!-- الهيدر -->
  <header class="header">
    <div class="header-top">
      <div class="logo-section">
        <div class="logo-icon">
          <i class="fas fa-graduation-cap"></i>
        </div>
        <div class="logo-text">
          <h1>أداة التقارير التعليمية</h1>
          <p>وزارة التعليم - نظام إعداد التقارير الذكي</p>
        </div>
      </div>
      <button class="mobile-menu-btn" onclick="toggleMenu()">
        <i class="fas fa-bars"></i>
      </button>
    </div>
    
    <div class="header-bottom">
      <div class="alert alert-success">
        <i class="fas fa-check-circle"></i>
        <span>جميع البيانات مؤمنة ومشفرة</span>
      </div>
      <div class="alert alert-info">
        <i class="fas fa-mobile-alt"></i>
        <span>متوافق مع جميع الأجهزة</span>
      </div>
    </div>
  </header>

  <!-- المحتوى الرئيسي -->
  <div class="main-content">
    <!-- نموذج الإدخال -->
    <main class="form-container">
      <div class="form-header">
        <h2><i class="fas fa-edit"></i> إعداد تقرير جديد</h2>
      </div>

      <div class="form-content">
        <!-- معلومات المدرسة -->
        <div class="form-section">
          <h3 class="form-section-title">
            <i class="fas fa-school"></i>
            معلومات المدرسة
          </h3>
          <div class="form-grid">
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-university"></i>
                اسم المدرسة
              </label>
              <input type="text" class="form-control" id="school-name" 
                     placeholder="أدخل اسم المدرسة الكامل" required>
            </div>
            
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-map-marker-alt"></i>
                إدارة التعليم
              </label>
              <select class="form-control" id="education-department">
                <option value="">اختر إدارة التعليم</option>
                <option value="الرياض">الإدارة العامة للتعليم بمنطقة الرياض</option>
                <option value="مكة">الإدارة العامة للتعليم بمنطقة مكة المكرمة</option>
                <option value="الشرقية">الإدارة العامة للتعليم بالمنطقة الشرقية</option>
                <option value="المدينة">الإدارة العامة للتعليم بمنطقة المدينة المنورة</option>
              </select>
            </div>
          </div>
        </div>

        <!-- معلومات التقرير -->
        <div class="form-section">
          <h3 class="form-section-title">
            <i class="fas fa-file-alt"></i>
            معلومات التقرير
          </h3>
          <div class="form-grid">
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-file"></i>
                نوع التقرير
              </label>
              <select class="form-control" id="report-type">
                <option value="اثرائي">تقرير نشاط إثرائي</option>
                <option value="علاجي">تقرير خطة علاجية</option>
                <option value="تقويمي">تقرير تقويمي</option>
                <option value="متابعة">تقرير متابعة</option>
              </select>
            </div>
            
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-users"></i>
                الفئة المستهدفة
              </label>
              <input type="text" class="form-control" id="target-audience" 
                     placeholder="مثال: طلاب الصف الثالث الثانوي">
            </div>
            
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-calendar"></i>
                الفصل الدراسي
              </label>
              <select class="form-control" id="semester">
                <option value="الأول">الفصل الدراسي الأول</option>
                <option value="الثاني">الفصل الدراسي الثاني</option>
                <option value="الصيفي">الفصل الصيفي</option>
              </select>
            </div>
            
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-book"></i>
                المادة الدراسية
              </label>
              <input type="text" class="form-control" id="subject" 
                     placeholder="مثال: الرياضيات">
            </div>
          </div>
        </div>

        <!-- محتوى التقرير -->
        <div class="form-section">
          <h3 class="form-section-title">
            <i class="fas fa-file-signature"></i>
            محتوى التقرير
          </h3>
          
          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-bullseye"></i>
              الهدف التربوي
            </label>
            <textarea class="form-control" id="educational-goal" 
                      placeholder="صغ الهدف التربوي من النشاط..." 
                      rows="3" required></textarea>
          </div>
          
          <div class="form-group">
            <label class="form-label">
              <i class="fas fa-tasks"></i>
              إجراءات التنفيذ
            </label>
            <textarea class="form-control" id="implementation-steps" 
                      placeholder="صف خطوات التنفيذ بالتفصيل..." 
                      rows="4"></textarea>
          </div>
          
          <div class="form-grid">
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-chart-line"></i>
                النتائج المتحققة
              </label>
              <textarea class="form-control" id="achieved-results" 
                        placeholder="ما هي النتائج التي تحققت؟" 
                        rows="3"></textarea>
            </div>
            
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-comments"></i>
                التوصيات والمقترحات
              </label>
              <textarea class="form-control" id="recommendations" 
                        placeholder="ما هي توصياتك للمستقبل؟" 
                        rows="3"></textarea>
            </div>
          </div>
          
          <div class="form-grid">
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-thumbs-up"></i>
                نقاط القوة
              </label>
              <textarea class="form-control" id="strengths" 
                        placeholder="ما هي نقاط القوة في النشاط؟" 
                        rows="2"></textarea>
            </div>
            
            <div class="form-group">
              <label class="form-label">
                <i class="fas fa-lightbulb"></i>
                فرص التحسين
              </label>
              <textarea class="form-control" id="improvements" 
                        placeholder="ما هي فرص التحسين؟" 
                        rows="2"></textarea>
            </div>
          </div>
        </div>

        <!-- الصور التوثيقية -->
        <div class="form-section">
          <h3 class="form-section-title">
            <i class="fas fa-images"></i>
            الصور التوثيقية
          </h3>
          
          <div class="upload-area" onclick="document.getElementById('image-upload').click()">
            <i class="fas fa-cloud-upload-alt"></i>
            <p>انقر أو اسحب الصور هنا</p>
            <small>يسمح بصورتين كحد أقصى (JPEG, PNG)</small>
          </div>
          
          <input type="file" id="image-upload" accept="image/*" multiple 
                 style="display: none" onchange="handleImageUpload(this)">
          
          <div class="image-preview" id="image-preview"></div>
        </div>

        <!-- التوقيعات -->
        <div class="signatures-section">
          <h3 class="form-section-title">
            <i class="fas fa-signature"></i>
            التوقيعات
          </h3>
          
          <div class="signatures-grid">
            <div class="signature-field">
              <label class="form-label">
                <i class="fas fa-chalkboard-teacher"></i>
                اسم المعلم
              </label>
              <input type="text" class="signature-input" id="teacher-name" 
                     placeholder="أدخل اسمك الكامل" required>
            </div>
            
            <div class="signature-field">
              <label class="form-label">
                <i class="fas fa-user-tie"></i>
                اسم المدير
              </label>
              <input type="text" class="signature-input" id="principal-name" 
                     placeholder="اسم مدير المدرسة">
            </div>
          </div>
        </div>
      </div>
    </main>

    <!-- لوحة التحكم -->
    <aside class="control-panel">
      <h3 class="form-section-title">
        <i class="fas fa-magic"></i>
        قوالب جاهزة
      </h3>
      
      <div class="quick-templates">
        <button class="template-btn" onclick="loadTemplate(1)">
          <i class="fas fa-star"></i>
          <span>نشاط إثرائي</span>
        </button>
        
        <button class="template-btn" onclick="loadTemplate(2)">
          <i class="fas fa-heart"></i>
          <span>خطة علاجية</span>
        </button>
        
        <button class="template-btn" onclick="loadTemplate(3)">
          <i class="fas fa-lightbulb"></i>
          <span>نشاط إبداعي</span>
        </button>
        
        <button class="template-btn" onclick="loadTemplate(4)">
          <i class="fas fa-chart-bar"></i>
          <span>تقرير تقويمي</span>
        </button>
      </div>
      
      <h3 class="form-section-title">
        <i class="fas fa-cogs"></i>
        أدوات التحكم
      </h3>
      
      <div class="action-buttons">
        <button class="action-btn action-btn-primary" onclick="showPreview()">
          <i class="fas fa-eye"></i>
          معاينة التقرير
        </button>
        
        <button class="action-btn action-btn-success" onclick="printReport()">
          <i class="fas fa-print"></i>
          طباعة التقرير
        </button>
        
        <button class="action-btn action-btn-secondary" onclick="saveDraft()">
          <i class="fas fa-save"></i>
          حفظ كمسودة
        </button>
        
        <button class="action-btn" style="background: #ef4444; color: white;" onclick="clearForm()">
          <i class="fas fa-trash"></i>
          مسح النموذج
        </button>
      </div>
      
      <div class="alert alert-warning" style="margin-top: 20px;">
        <i class="fas fa-info-circle"></i>
        <span>يتم الحفظ تلقائياً في ذاكرة المتصفح</span>
      </div>
    </aside>
  </div>
</div>

<!-- شريط التنقل السفلي للجوال -->
<nav class="mobile-nav">
  <button class="nav-btn active" onclick="scrollToTop()">
    <i class="fas fa-home"></i>
    <span>الرئيسية</span>
  </button>
  
  <button class="nav-btn" onclick="showPreview()">
    <i class="fas fa-eye"></i>
    <span>معاينة</span>
  </button>
  
  <button class="nav-btn" onclick="printReport()">
    <i class="fas fa-print"></i>
    <span>طباعة</span>
  </button>
  
  <button class="nav-btn" onclick="saveDraft()">
    <i class="fas fa-save"></i>
    <span>حفظ</span>
  </button>
</nav>

<!-- نافذة المعاينة -->
<div class="preview-overlay" id="preview-overlay">
  <div class="preview-container">
    <div class="preview-header">
      <h3><i class="fas fa-file-pdf"></i> معاينة التقرير</h3>
      <button class="close-preview" onclick="hidePreview()">
        <i class="fas fa-times"></i>
      </button>
    </div>
    <div class="report-content" id="report-content">
      <!-- محتوى التقرير -->
    </div>
  </div>
</div>

<!-- شاشة التحميل -->
<div class="loading-overlay" id="loading-overlay">
  <div class="loading-spinner"></div>
  <p>جاري إنشاء التقرير...</p>
</div>

<script>
// بيانات التطبيق
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
    target: "طلاب الصف الثالث الثانوي المتميزين",
    subject: "الفيزياء"
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
    target: "الطلاب المتأخرين دراسياً في اللغة العربية",
    subject: "اللغة العربية"
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
    target: "طلاب المرحلة الثانوية المهتمين بالتكنولوجيا",
    subject: "الحاسب الآلي"
  },
  4: {
    name: "تقرير تقويمي",
    type: "تقويمي",
    goal: "تقويم أداء الطلاب في نهاية الفصل الدراسي وتحديد مستوى تحقيق الأهداف التعليمية.",
    steps: `1. إعداد اختبارات تقويمية شاملة
2. تحليل نتائج الاختبارات
3. مقابلات فردية مع الطلاب
4. دراسة مؤشرات الأداء
5. تقييم المنهج الدراسي`,
    results: `• تحقيق 85% من الطلاب للمستوى المطلوب
• تحسن في متوسط الدرجات بنسبة 15%
• ارتفاع مؤشر الرضا عن التعليم
• تحديد نقاط القوة والضعف`,
    recommendations: `• تطوير استراتيجيات التدريس
• تحسين الوسائل التعليمية
• تنويع أساليب التقويم
• تعزيز التعلم الذاتي`,
    target: "جميع طلاب الصف",
    subject: "الرياضيات"
  }
};

let uploadedImages = [];

// تحميل القالب
function loadTemplate(templateId) {
  const template = templates[templateId];
  if (!template) return;
  
  // تعبئة الحقول
  document.getElementById('report-type').value = template.type;
  document.getElementById('educational-goal').value = template.goal;
  document.getElementById('implementation-steps').value = template.steps;
  document.getElementById('achieved-results').value = template.results;
  document.getElementById('recommendations').value = template.recommendations;
  document.getElementById('target-audience').value = template.target;
  document.getElementById('subject').value = template.subject;
  
  // إضافة قيم افتراضية
  if (!document.getElementById('school-name').value) {
    document.getElementById('school-name').value = "مدرسة الملك عبدالله الثانوية";
  }
  if (!document.getElementById('teacher-name').value) {
    document.getElementById('teacher-name').value = "أحمد محمد علي";
  }
  if (!document.getElementById('principal-name').value) {
    document.getElementById('principal-name').value = "خالد بن عبدالله السليم";
  }
  
  showAlert(`تم تحميل قالب "${template.name}" بنجاح`, 'success');
}

// مسح النموذج
function clearForm() {
  if (!confirm('هل أنت متأكد من رغبتك في مسح جميع البيانات؟')) return;
  
  const fields = [
    'school-name', 'target-audience', 'educational-goal',
    'implementation-steps', 'achieved-results', 'recommendations',
    'teacher-name', 'principal-name', 'subject', 'strengths', 'improvements'
  ];
  
  fields.forEach(fieldId => {
    document.getElementById(fieldId).value = '';
  });
  
  // مسح الصور
  uploadedImages = [];
  document.getElementById('image-preview').innerHTML = '';
  document.getElementById('image-upload').value = '';
  
  // إعادة تعيين القوائم المنسدلة
  document.getElementById('report-type').value = 'اثرائي';
  document.getElementById('education-department').value = '';
  document.getElementById('semester').value = 'الأول';
  
  showAlert('تم مسح جميع البيانات بنجاح', 'success');
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
    if (!file.type.match('image.*')) {
      showAlert('يرجى رفع ملفات صور فقط', 'error');
      return;
    }
    
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
        <div class="remove-image" onclick="removeImage(${index})">
          <i class="fas fa-times"></i>
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
      <div class="remove-image" onclick="removeImage(${i})">
        <i class="fas fa-times"></i>
      </div>
    `;
    preview.appendChild(imgDiv);
  });
}

// عرض المعاينة
function showPreview() {
  const data = collectFormData();
  
  if (!validateForm()) {
    showAlert('الرجاء تعبئة الحقول المطلوبة (اسم المدرسة، الهدف التربوي، اسم المعلم)', 'error');
    return;
  }
  
  buildPreviewContent(data);
  document.getElementById('preview-overlay').style.display = 'flex';
  document.body.style.overflow = 'hidden';
}

// إخفاء المعاينة
function hidePreview() {
  document.getElementById('preview-overlay').style.display = 'none';
  document.body.style.overflow = 'auto';
}

// طباعة التقرير
function printReport() {
  const data = collectFormData();
  
  if (!validateForm()) {
    showAlert('الرجاء تعبئة الحقول المطلوبة قبل الطباعة', 'error');
    return;
  }
  
  // إنشاء نافذة طباعة
  const printWindow = window.open('', '_blank');
  printWindow.document.write(`
    <!DOCTYPE html>
    <html dir="rtl" lang="ar">
    <head>
      <meta charset="UTF-8">
      <title>تقرير تعليمي - ${data.school}</title>
      <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700&display=swap');
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { 
          font-family: 'Cairo', sans-serif; 
          line-height: 1.6; 
          color: #1f2937; 
          padding: 20px;
          max-width: 210mm;
          margin: 0 auto;
        }
        .report-header { 
          text-align: center; 
          margin-bottom: 30px; 
          padding-bottom: 20px; 
          border-bottom: 3px solid #1a56db; 
        }
        .report-header h1 { color: #1a56db; font-size: 24px; margin-bottom: 10px; }
        .report-header h2 { color: #1f2937; font-size: 18px; margin-bottom: 5px; }
        .report-header h3 { color: #6b7280; font-size: 16px; margin-bottom: 10px; }
        .report-date { color: #6b7280; font-size: 14px; margin-top: 10px; }
        .report-section { margin-bottom: 25px; page-break-inside: avoid; }
        .report-section-title { 
          color: #1f2937; 
          font-size: 18px; 
          margin-bottom: 15px; 
          padding-right: 10px; 
          border-right: 3px solid #1a56db; 
        }
        .report-section-content { 
          color: #1f2937; 
          line-height: 1.8; 
          background: #f9fafb; 
          padding: 15px; 
          border-radius: 8px; 
          white-space: pre-line;
        }
        .report-grid { 
          display: grid; 
          grid-template-columns: 1fr 1fr; 
          gap: 20px; 
          margin-bottom: 25px;
        }
        @media (max-width: 768px) {
          .report-grid { grid-template-columns: 1fr; }
        }
        .report-images { 
          display: grid; 
          grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
          gap: 15px; 
          margin-top: 15px;
        }
        .report-image { 
          border: 1px solid #e5e7eb; 
          border-radius: 8px; 
          overflow: hidden; 
        }
        .report-image img { 
          width: 100%; 
          height: 150px; 
          object-fit: cover; 
        }
        .report-signatures { 
          display: flex; 
          justify-content: space-between; 
          margin-top: 40px; 
          padding-top: 20px; 
          border-top: 1px solid #e5e7eb;
        }
        .signature-box { text-align: center; flex: 1; }
        .signature-name { font-size: 16px; font-weight: 600; color: #1f2937; margin-top: 15px; }
        .signature-line { width: 150px; height: 1px; background: #e5e7eb; margin: 10px auto; }
        @media print {
          body { padding: 0; }
          .report-header { border-bottom-width: 2px; }
          .report-section-content { background: none; padding: 10px; }
        }
      </style>
    </head>
    <body>
      ${generateReportHTML(data)}
    </body>
    </html>
  `);
  
  printWindow.document.close();
  printWindow.focus();
  
  setTimeout(() => {
    printWindow.print();
    printWindow.close();
  }, 500);
}

// حفظ المسودة
function saveDraft() {
  const data = collectFormData();
  
  try {
    localStorage.setItem('report_draft', JSON.stringify({
      ...data,
      images: uploadedImages,
      timestamp: new Date().toISOString()
    }));
    
    showAlert('تم حفظ المسودة بنجاح في ذاكرة المتصفح', 'success');
  } catch (e) {
    showAlert('حدث خطأ أثناء حفظ المسودة', 'error');
  }
}

// تحميل المسودة
function loadDraft() {
  try {
    const draft = JSON.parse(localStorage.getItem('report_draft'));
    if (!draft) return;
    
    if (confirm('تم العثور على مسودة محفوظة. هل تريد تحميلها؟')) {
      document.getElementById('school-name').value = draft.school || '';
      document.getElementById('education-department').value = draft.department || '';
      document.getElementById('report-type').value = draft.type || 'اثرائي';
      document.getElementById('target-audience').value = draft.target || '';
      document.getElementById('semester').value = draft.semester || 'الأول';
      document.getElementById('subject').value = draft.subject || '';
      document.getElementById('educational-goal').value = draft.goal || '';
      document.getElementById('implementation-steps').value = draft.steps || '';
      document.getElementById('achieved-results').value = draft.results || '';
      document.getElementById('recommendations').value = draft.recommendations || '';
      document.getElementById('strengths').value = draft.strengths || '';
      document.getElementById('improvements').value = draft.improvements || '';
      document.getElementById('teacher-name').value = draft.teacher || '';
      document.getElementById('principal-name').value = draft.principal || '';
      
      if (draft.images && draft.images.length > 0) {
        uploadedImages = draft.images;
        updateImagePreview();
      }
      
      showAlert('تم تحميل المسودة بنجاح', 'success');
    }
  } catch (e) {
    console.error('خطأ في تحميل المسودة:', e);
  }
}

// تحديث معاينة الصور
function updateImagePreview() {
  const preview = document.getElementById('image-preview');
  preview.innerHTML = '';
  
  uploadedImages.forEach((img, i) => {
    const imgDiv = document.createElement('div');
    imgDiv.className = 'preview-image';
    imgDiv.innerHTML = `
      <img src="${img.data}" alt="صورة ${i + 1}">
      <div class="remove-image" onclick="removeImage(${i})">
        <i class="fas fa-times"></i>
      </div>
    `;
    preview.appendChild(imgDiv);
  });
}

// جمع بيانات النموذج
function collectFormData() {
  return {
    department: document.getElementById('education-department').value,
    school: document.getElementById('school-name').value.trim(),
    type: document.getElementById('report-type').value,
    target: document.getElementById('target-audience').value.trim(),
    semester: document.getElementById('semester').value,
    subject: document.getElementById('subject').value.trim(),
    goal: document.getElementById('educational-goal').value.trim(),
    steps: document.getElementById('implementation-steps').value.trim(),
    results: document.getElementById('achieved-results').value.trim(),
    recommendations: document.getElementById('recommendations').value.trim(),
    strengths: document.getElementById('strengths').value.trim(),
    improvements: document.getElementById('improvements').value.trim(),
    teacher: document.getElementById('teacher-name').value.trim(),
    principal: document.getElementById('principal-name').value.trim()
  };
}

// التحقق من صحة البيانات
function validateForm() {
  const data = collectFormData();
  const requiredFields = ['school', 'goal', 'teacher'];
  
  for (const field of requiredFields) {
    if (!data[field]) {
      return false;
    }
  }
  
  return true;
}

// بناء محتوى التقرير
function buildPreviewContent(data) {
  const content = document.getElementById('report-content');
  content.innerHTML = generateReportHTML(data);
}

// توليد HTML للتقرير
function generateReportHTML(data) {
  const getDepartmentName = (value) => {
    const departments = {
      'الرياض': 'الإدارة العامة للتعليم بمنطقة الرياض',
      'مكة': 'الإدارة العامة للتعليم بمنطقة مكة المكرمة',
      'الشرقية': 'الإدارة العامة للتعليم بالمنطقة الشرقية',
      'المدينة': 'الإدارة العامة للتعليم بمنطقة المدينة المنورة'
    };
    return departments[value] || value;
  };

  const getReportTypeName = (type) => {
    const types = {
      'اثرائي': 'تقرير نشاط إثرائي',
      'علاجي': 'تقرير خطة علاجية',
      'تقويمي': 'تقرير تقويمي',
      'متابعة': 'تقرير متابعة'
    };
    return types[type] || 'تقرير تعليمي';
  };

  const getCurrentDate = () => {
    const now = new Date();
    const date = now.getDate().toString().padStart(2, '0');
    const month = (now.getMonth() + 1).toString().padStart(2, '0');
    const year = now.getFullYear();
    const hijriYear = 1446;
    
    return `${date}/${month}/${year} م - ${hijriYear} هـ`;
  };

  return `
    <div class="report-header">
      <h1>وزارة التعليم</h1>
      <h2>${getDepartmentName(data.department)}</h2>
      <h3>${data.school}</h3>
      <div class="report-date">
        ${getCurrentDate()} | ${getReportTypeName(data.type)} | الفصل ${data.semester}
      </div>
    </div>
    
    <div class="report-section">
      <div class="report-section-title">المعلومات الأساسية</div>
      <div class="report-section-content">
        <strong>المادة الدراسية:</strong> ${data.subject || 'غير محدد'}<br>
        <strong>الفئة المستهدفة:</strong> ${data.target || 'غير محدد'}<br>
        <strong>الفصل الدراسي:</strong> الفصل ${data.semester}
      </div>
    </div>
    
    <div class="report-section">
      <div class="report-section-title">الهدف التربوي</div>
      <div class="report-section-content">${data.goal}</div>
    </div>
    
    <div class="report-section">
      <div class="report-section-title">إجراءات التنفيذ</div>
      <div class="report-section-content">${data.steps || 'لم يتم تحديد إجراءات التنفيذ'}</div>
    </div>
    
    <div class="report-grid">
      <div class="report-section">
        <div class="report-section-title">النتائج المتحققة</div>
        <div class="report-section-content">${data.results || 'لم يتم تحديد النتائج'}</div>
      </div>
      
      <div class="report-section">
        <div class="report-section-title">التوصيات والمقترحات</div>
        <div class="report-section-content">${data.recommendations || 'لم يتم تحديد توصيات'}</div>
      </div>
    </div>
    
    <div class="report-grid">
      <div class="report-section">
        <div class="report-section-title">نقاط القوة</div>
        <div class="report-section-content">${data.strengths || 'لم يتم تحديد نقاط القوة'}</div>
      </div>
      
      <div class="report-section">
        <div class="report-section-title">فرص التحسين</div>
        <div class="report-section-content">${data.improvements || 'لم يتم تحديد فرص التحسين'}</div>
      </div>
    </div>
    
    ${uploadedImages.length > 0 ? `
      <div class="report-section">
        <div class="report-section-title">الصور التوثيقية</div>
        <div class="report-images">
          ${uploadedImages.map(img => `
            <div class="report-image">
              <img src="${img.data}" alt="صورة توثيقية">
            </div>
          `).join('')}
        </div>
      </div>
    ` : ''}
    
    <div class="report-signatures">
      <div class="signature-box">
        <div class="signature-name">المعلم</div>
        <div class="signature-line"></div>
        <div>${data.teacher}</div>
      </div>
      
      <div class="signature-box">
        <div class="signature-name">مدير المدرسة</div>
        <div class="signature-line"></div>
        <div>${data.principal || '.................'}</div>
      </div>
    </div>
  `;
}

// عرض التنبيهات
function showAlert(message, type = 'info') {
  const alert = document.createElement('div');
  alert.className = `alert alert-${type}`;
  alert.innerHTML = `
    <i class="fas fa-${type === 'success' ? 'check-circle' : 
                      type === 'warning' ? 'exclamation-triangle' : 
                      type === 'error' ? 'times-circle' : 'info-circle'}"></i>
    <span>${message}</span>
  `;
  
  const container = document.querySelector('.container');
  container.prepend(alert);
  
  setTimeout(() => {
    if (alert.parentNode) {
      alert.remove();
    }
  }, 5000);
}

// وظائف القائمة الجوال
function scrollToTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' });
  setActiveNavBtn(0);
}

function setActiveNavBtn(index) {
  const navBtns = document.querySelectorAll('.nav-btn');
  navBtns.forEach((btn, i) => {
    if (i === index) {
      btn.classList.add('active');
    } else {
      btn.classList.remove('active');
    }
  });
}

function toggleMenu() {
  const controlPanel = document.querySelector('.control-panel');
  controlPanel.style.display = controlPanel.style.display === 'none' ? 'block' : 'none';
}

// إغلاق التنبيه بالنقر
document.addEventListener('click', function(e) {
  if (e.target.closest('.alert')) {
    e.target.closest('.alert').remove();
  }
});

// إغلاق المعاينة بالزر ESC
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') {
    hidePreview();
  }
});

// إغلاق المعاينة بالنقر خارجها
document.getElementById('preview-overlay').addEventListener('click', function(e) {
  if (e.target === this) {
    hidePreview();
  }
});

// تحسين تجربة اللمس
document.addEventListener('DOMContentLoaded', function() {
  // تحميل المسودة عند البدء
  loadDraft();
  
  // تعيين القيم الافتراضية إذا لم تكن موجودة
  if (!document.getElementById('school-name').value) {
    document.getElementById('school-name').value = "مدرسة الملك عبدالله الثانوية";
  }
  
  // إضافة مستمعين للأزرار في الجوال
  const navBtns = document.querySelectorAll('.nav-btn');
  navBtns.forEach((btn, index) => {
    btn.addEventListener('click', () => setActiveNavBtn(index));
  });
  
  // الترحيب
  setTimeout(() => {
    showAlert('مرحباً بك في نظام إعداد التقارير التعليمية', 'success');
  }, 1000);
});

// دعم سحب وإفلات الصور
const uploadArea = document.querySelector('.upload-area');
uploadArea.addEventListener('dragover', (e) => {
  e.preventDefault();
  uploadArea.style.borderColor = '#1a56db';
  uploadArea.style.background = '#f3f4f6';
});

uploadArea.addEventListener('dragleave', () => {
  uploadArea.style.borderColor = '';
  uploadArea.style.background = '';
});

uploadArea.addEventListener('drop', (e) => {
  e.preventDefault();
  uploadArea.style.borderColor = '';
  uploadArea.style.background = '';
  
  const files = Array.from(e.dataTransfer.files);
  const input = document.getElementById('image-upload');
  input.files = e.dataTransfer.files;
  handleImageUpload(input);
});
</script>
</body>
</html>