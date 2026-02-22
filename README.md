<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<title>تقرير إداري PDF</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap');

@page{
  size:A4;
  margin:10mm;
}

:root{
  --main:#062f25;
  --border:#2f9e8f;
}

body{
  margin:0;
  font-family:'Cairo',sans-serif;
  background:#fff;
}

.whatsapp-btn{
  position:fixed;
  bottom:18px;
  left:18px;
  background:#25D366;
  color:#fff;
  border:none;
  border-radius:40px;
  padding:10px 18px;
  font-size:13px;
  font-weight:700;
  cursor:pointer;
  z-index:999;
}

#report-content{
  width:100%;
  max-width:210mm;
  margin:4mm auto 0 auto;
  padding:0 6mm;
  box-sizing:border-box;
}

/* الهيدر */
.header{
  background:var(--main);
  height:150px;
  border-radius:8px;
  color:#fff;
  display:flex;
  align-items:center;
  justify-content:center;
  position:relative;
  margin-bottom:8px;
}
.header img{width:140px;}
.header-school{position:absolute;right:12px;bottom:18px;font-size:12px;font-weight:700;}
.header-education{position:absolute;left:50%;bottom:6px;transform:translateX(-50%);font-size:10px;}
.header-date{position:absolute;left:12px;top:10px;font-size:9px;text-align:right;}

/* مربعات المعلومات */
.info-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:6px;
  margin-bottom:6px;
}
.info-grid2{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:6px;
  margin-bottom:6px;
}

.info-box{
  border:1px solid var(--border);
  border-radius:7px;
  padding:14px 4px 6px;
  position:relative;
  text-align:center;
  font-size:10px;
  min-height:34px;
}
.info-title{
  position:absolute;
  top:4px;
  right:50%;
  transform:translateX(50%);
  font-size:8px;
  font-weight:700;
  color:var(--main);
}
.info-value{
  font-size:10px;
  font-weight:600;
}

/* الهدف */
.box-objective{
  border:1px solid var(--border);
  border-radius:8px;
  padding:8px;
  margin-bottom:6px;
  height:110px;
}
.box-objective .box-title{
  text-align:center;
  color:var(--main);
  font-weight:700;
  font-size:11px;
  margin-bottom:4px;
}
.box-objective .box-content{
  font-size:11px;
  line-height:1.5;
  text-align:center;
}

/* المربعات */
.box{
  border:1px solid var(--border);
  border-radius:8px;
  padding:8px;
  margin-bottom:6px;
  height:150px;
}
.box-title{
  text-align:center;
  color:var(--main);
  font-weight:700;
  font-size:11px;
  margin-bottom:4px;
}
.box-content{
  font-size:11px;
  line-height:1.5;
  text-align:center;
}

.row{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:6px;
}

/* الصور */
.images{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:6px;
  margin-bottom:6px;
}
.image-box{
  border:1px dashed var(--border);
  height:125px;
  display:flex;
  align-items:center;
  justify-content:center;
}

/* التوقيع */
.signatures{
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:30px;
  text-align:center;
  font-size:10px;
  margin-bottom:6px;
}
.signature-role{
  font-size:9px;
  color:var(--main);
  font-weight:600;
}
.signature-name{
  font-size:11px;
  font-weight:700;
}
.sign-line{
  border-top:1px solid #000;
  margin:6px auto 0;
  width:70%;
}

.footer-box{
  background:var(--main);
  color:#fff;
  text-align:center;
  font-size:8px;
  padding:3px 4px;
  border-radius:6px;
}
</style>
</head>

<body>

<button class="whatsapp-btn" onclick="sendPDF()">إرسال PDF عبر واتساب</button>

<div id="report-content">

<div class="header">
  <img src="https://i.ibb.co/1fc5gB6v/9-C92-E57-B-23-FA-479-D-A024-1-D5-F871-B4-F8-D.png">
  <div class="header-school">اسم المدرسة</div>
  <div class="header-education">إدارة التعليم</div>
  <div class="header-date">1447 هـ<br>2026 م</div>
</div>

<div class="info-grid">
  <div class="info-box"><div class="info-title">الفصل الدراسي</div><div class="info-value">الأول</div></div>
  <div class="info-box"><div class="info-title">اسم التقرير</div><div class="info-value">تقرير إداري</div></div>
  <div class="info-box"><div class="info-title">المجال</div><div class="info-value">تربوي</div></div>
  <div class="info-box"><div class="info-title">المستهدفون</div><div class="info-value">المعلمين</div></div>
</div>

<div class="info-grid2">
  <div class="info-box"><div class="info-title">المبادرة</div><div class="info-value">تهيئة الطلاب</div></div>
  <div class="info-box"><div class="info-title">مكان التنفيذ</div><div class="info-value">داخل المدرسة</div></div>
  <div class="info-box"><div class="info-title">مدة التنفيذ</div><div class="info-value">يوم واحد</div></div>
</div>

<div class="box-objective">
  <div class="box-title">الأهداف</div>
  <div class="box-content"></div>
</div>

<div class="row">
  <div class="box"><div class="box-title">الإجراءات المنفذة</div><div class="box-content"></div></div>
  <div class="box"><div class="box-title">النتائج</div><div class="box-content"></div></div>
</div>

<div class="row">
  <div class="box"><div class="box-title">نقاط القوة</div><div class="box-content"></div></div>
  <div class="box"><div class="box-title">أولويات التطوير</div><div class="box-content"></div></div>
</div>

<div class="row">
  <div class="box"><div class="box-title">التوصيات</div><div class="box-content"></div></div>
  <div class="box"><div class="box-title">خطة المتابعة</div><div class="box-content"></div></div>
</div>

<div class="images">
  <div class="image-box"></div>
  <div class="image-box"></div>
</div>

<div class="signatures">
  <div>
    <div class="signature-role">معد التقرير</div>
    <div class="signature-name">فهد الخالدي</div>
    <div class="sign-line"></div>
  </div>
  <div>
    <div class="signature-role">قائد المدرسة</div>
    <div class="signature-name">نايف اللحياني</div>
    <div class="sign-line"></div>
  </div>
</div>

<div class="footer-box">
  وزارة التعليم – المملكة العربية السعودية
</div>

</div>

<script>
async function sendPDF(){
  const element=document.getElementById('report-content');

  const pdf=await html2pdf().set({
    margin:0,
    html2canvas:{scale:2,useCORS:true},
    jsPDF:{unit:'mm',format:'a4',orientation:'portrait'}
  }).from(element).toPdf().output('blob');

  const file=new File([pdf],'report.pdf',{type:'application/pdf'});

  if(navigator.canShare && navigator.canShare({files:[file]})){
    navigator.share({files:[file],title:'تقرير إداري'});
  }else{
    const link=document.createElement("a");
    link.href=URL.createObjectURL(pdf);
    link.download="report.pdf";
    link.click();
    window.open("https://wa.me/?text="+encodeURIComponent("تم إنشاء التقرير، الرجاء إرفاق ملف PDF."),"_blank");
  }
}
</script>

</body>
</html>