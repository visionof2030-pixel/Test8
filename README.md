<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <title>HTML to PDF (Arabic)</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      padding: 20px;
    }
    textarea {
      width: 100%;
      height: 200px;
      font-size: 16px;
      direction: rtl;
    }
    button {
      margin-top: 10px;
      padding: 10px 20px;
      font-size: 16px;
    }
  </style>
</head>
<body>

  <h3>اكتب نص HTML (عربي)</h3>
  <textarea id="htmlInput">
<h1>مرحبا</h1>
<p>هذا مثال على نص عربي يتم تصديره إلى ملف PDF مع دعم صحيح للغة العربية.</p>
  </textarea>
  <button onclick="generatePDF()">تصدير PDF</button>

  <script src="https://unpkg.com/pdf-lib/dist/pdf-lib.min.js"></script>
  <script src="https://unpkg.com/@pdf-lib/fontkit/dist/fontkit.umd.js"></script>
  <script src="https://unpkg.com/arabic-persian-reshaper"></script>
  <script src="https://unpkg.com/bidi-js/dist/bidi.js"></script>

  <script>
    async function generatePDF() {
      const { PDFDocument } = PDFLib;
      const html = document.getElementById("htmlInput").value;

      const reshapedText = ArabicPersianReshaper.reshape(html.replace(/<[^>]*>/g, ""));
      const bidi = new Bidi();
      const finalText = bidi.getReorderedString(reshapedText);

      const pdfDoc = await PDFDocument.create();
      pdfDoc.registerFontkit(fontkit);

      const fontBytes = await fetch("https://fonts.gstatic.com/s/amiri/v27/J7aRnpd8CGxBHpUrtLMA7w.ttf").then(r => r.arrayBuffer());
      const arabicFont = await pdfDoc.embedFont(fontBytes);

      const page = pdfDoc.addPage();
      const { width, height } = page.getSize();

      page.drawText(finalText, {
        x: width - 50,
        y: height - 50,
        size: 16,
        font: arabicFont,
        maxWidth: width - 100,
        lineHeight: 24,
        direction: "rtl"
      });

      const pdfBytes = await pdfDoc.save();
      const blob = new Blob([pdfBytes], { type: "application/pdf" });
      const link = document.createElement("a");
      link.href = URL.createObjectURL(blob);
      link.download = "arabic.pdf";
      link.click();
    }
  </script>

</body>
</html>