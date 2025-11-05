<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>مشروع أفق </title>
  <style>
    body {
      margin: 0;
      min-height: 100vh;
      background: linear-gradient(270deg, #a8d0ff, #ffffff, #a8d0ff);
      background-size: 600% 600%;
      animation: gradientAnimation 15s ease infinite;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      padding: 50px 20px;
      box-sizing: border-box;
      flex-direction: column;
      align-items: center;
    }

 
    .container {
      width: 95%;
      max-width: 1200px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    h1 {
      font-size: 60px;
      color: #004080;
      margin: 0 0 20px 0;
      text-align: center;
      opacity: 0;
      animation: fadeIn 2s forwards;
    }

    /* فقرة تحت العنوان */
    .subtitle {
      margin-bottom: 30px;
      text-align: center;
      font-size: 20px;
      color: #003366;
      opacity: 0;
      animation: fadeIn 2s forwards;
      animation-delay: 1s;
    }

    /* البطاقات */
    .cards-container {
      display: flex;
      gap: 20px;
      flex-wrap: wrap;
      justify-content: center;
      width: 100%;
    }

    .card {
      flex: 1 1 200px;
      max-width: 300px;
      height: 120px;
      background-color: #4facfe;
      color: white;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.5s ease;
      overflow: hidden;
      position: relative;
    }

    .card.expanded {
      flex: 1 1 500px;
      height: 300px;
      max-width: 500px;
      background-color: #00f2fe;
    }

    /* النص "اضغط للتوسع" يختفي عند التوسيع */
    .card-title {
      transition: opacity 0.3s ease;
    }
    .card.expanded .card-title {
      display: none;
    }

    .card .content {
      opacity: 0;
      transition: opacity 0.5s ease;
      padding: 10px;
      position: absolute;
      top: 50px;
      left: 0;
      right: 0;
    }

    .card.expanded .content {
      opacity: 1;
    }

    /* صورة أسفل البطاقات (انميشن)*/
    .image-container {
      margin-top: 40px;
      text-align: center;
      opacity: 0;
      transform: translateY(20px);
      animation: fadeInUp 2s forwards;
      animation-delay: 0.5s;
      width: 100%;
    }

    .image-container img {
      max-width: 100%;
      height: auto;
      border-radius: 10px;
    }

    /* حركة التدرج */
    @keyframes gradientAnimation {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    /* حركة ظهور العنوان والفقرة */
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(-20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* حركة ظهور الصورة مع رفعها */
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    /* Media Queries للأجهزة الصغيرة */
    @media (max-width: 768px) {
      h1 { font-size: 40px; }
      .subtitle { font-size: 18px; }
      .card { height: 100px; }
      .card.expanded { height: 250px; }
    }

    @media (max-width: 480px) {
      h1 { font-size: 32px; }
      .subtitle { font-size: 16px; }
      .card { flex: 1 1 100%; max-width: 100%; }
      .card.expanded { max-width: 100%; }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>أفق</h1>

    <!-- فقرة تحت العنوان -->
    <div class="subtitle">
      <p>مرحبا بك.أفق هو نظام ذكاء اصطناعي هدفه الأول والأخير هو مساعدتك في إدارة مشروعك. .</p>
    </div>

    <!-- البطاقات -->
    <div class="cards-container">
      <div class="card" onclick="toggleCard(this)">
        <div class="card-title">الشعار</div>
        <div class="content">
          <h2>الشعار</h2>
          <p> صنع الشعار من قبل(المجموعة الاولى) 
          صمم بعناية حيث يحمل عده
          معاني يرمز الاسم إلى التوسع والافق التي لا نهايه لها ويرمز اللون الازرق للزدهار    </p>
        </div>
      </div>
      
      
      <!-- البطاقات -->
    <div class="cards-container">
      <div class="card" onclick="toggleCard(this)">
        <div class="card-title">الفريق المسؤول </div>
        <div class="content">
          <h2> الفريق المسؤول </h2>
          <p> تم الاشراف على المشروع من قبل الاستاذه بدريه العنزي وتم تنفيذه من قبل طالبات المجموعة الاولى (ندى فيصل، رغد عبدالله، لميس عبدالله، عيدة الرشيدي) </p>
        </div>
      </div>
    </div>

    <!-- صورة أسفل البطاقات -->
    <div class="image-container">
      <img src="افق.png" alt="صورة توضيحية">
    </div>
  </div>

  <script>
    function toggleCard(card) {
      card.classList.toggle('expanded');
    }
  </script>
</body>
</html>
