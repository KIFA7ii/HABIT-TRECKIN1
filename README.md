# HABIT-TRECKIN1
[habit.html](https://github.com/user-attachments/files/25096282/habit.html)
<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Habit Tracker | متتبع العادات الذكي</title>
  <meta name="description" content="متتبع عادات ذكي لـ Excel و Google Sheets مع لوحات تحكم ورسوم تلقائية وتتبع الستريك." />

  <style>
    :root{
      --bg:#0b1220;
      --card:#0f1a2d;
      --muted:#a9b6d3;
      --text:#eaf0ff;
      --accent:#22c55e;
      --accent2:#60a5fa;
      --line:rgba(255,255,255,.10);
      --shadow: 0 20px 60px rgba(0,0,0,.35);
      --radius:22px;
      --max:1100px;
      --font: system-ui, -apple-system, Segoe UI, Roboto, "Noto Sans Arabic", "Tahoma", Arial, sans-serif;
    }
    *{box-sizing:border-box}
    body{
      margin:0;
      font-family:var(--font);
      background: radial-gradient(1200px 600px at 70% -10%, rgba(96,165,250,.20), transparent 60%),
                  radial-gradient(900px 500px at 10% 0%, rgba(34,197,94,.18), transparent 55%),
                  var(--bg);
      color:var(--text);
      line-height:1.6;
    }
    a{color:inherit}
    .wrap{max-width:var(--max); margin:0 auto; padding:26px 18px 90px;}
    .nav{
      display:flex; align-items:center; justify-content:space-between;
      gap:12px; padding:10px 0 22px;
    }
    .brand{
      display:flex; align-items:center; gap:10px; font-weight:800; letter-spacing:.2px;
    }
    .logo{
      width:42px; height:42px; border-radius:14px;
      background: linear-gradient(135deg, rgba(34,197,94,.95), rgba(96,165,250,.95));
      box-shadow: 0 10px 30px rgba(34,197,94,.18);
    }
    .nav a.btn{
      text-decoration:none; padding:10px 14px; border-radius:999px;
      background: rgba(255,255,255,.08);
      border:1px solid var(--line);
    }
    .grid{
      display:grid; gap:18px;
    }
    .hero{
      grid-template-columns: 1.1fr .9fr;
      align-items:center;
      gap:22px;
      padding:18px 0 10px;
    }
    @media (max-width: 900px){
      .hero{grid-template-columns: 1fr; }
    }
    .kicker{
      display:inline-flex; gap:8px; align-items:center;
      padding:8px 12px; border-radius:999px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.06);
      color: var(--muted);
      width:fit-content;
      font-size:14px;
    }
    .kicker b{color:var(--text)}
    h1{
      margin:12px 0 10px;
      font-size: clamp(30px, 4vw, 52px);
      line-height:1.15;
      letter-spacing:.2px;
    }
    .sub{
      margin:0 0 16px;
      color: var(--muted);
      font-size: clamp(16px, 1.7vw, 18px);
      max-width: 52ch;
    }
    .ctaRow{display:flex; gap:10px; flex-wrap:wrap; margin-top:14px}
    .btn{
      display:inline-flex; align-items:center; justify-content:center; gap:10px;
      padding:12px 16px;
      border-radius:999px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.06);
      text-decoration:none;
      font-weight:700;
      cursor:pointer;
      transition: transform .15s ease, background .15s ease;
    }
    .btn:hover{transform: translateY(-1px); background: rgba(255,255,255,.09);}
    .btn.primary{
      background: linear-gradient(135deg, rgba(34,197,94,.95), rgba(96,165,250,.70));
      border:0;
      box-shadow: 0 18px 55px rgba(34,197,94,.18);
      color:#071018;
    }
    .pillRow{
      display:flex; gap:10px; flex-wrap:wrap; margin-top:14px;
      color: var(--muted); font-size:14px;
    }
    .pill{padding:8px 10px; border-radius:999px; border:1px solid var(--line); background: rgba(255,255,255,.04);}
    .card{
      background: rgba(15,26,45,.65);
      border:1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow:hidden;
    }
    .media{
      padding:12px;
    }
    .media img{
      width:100%;
      display:block;
      border-radius: 16px;
      border:1px solid rgba(255,255,255,.08);
      background: rgba(255,255,255,.02);
    }
    .section{margin-top:26px;}
    .section h2{
      margin:0 0 10px;
      font-size: clamp(22px, 2.6vw, 30px);
    }
    .section p{margin:0; color:var(--muted)}
    .features{
      grid-template-columns: repeat(3, 1fr);
      margin-top:14px;
    }
    @media (max-width: 900px){
      .features{grid-template-columns: 1fr;}
    }
    .feat{
      padding:16px;
    }
    .feat .icon{
      width:40px;height:40px;border-radius:14px;
      display:grid;place-items:center;
      background: rgba(255,255,255,.07);
      border:1px solid var(--line);
      margin-bottom:10px;
      font-size:18px;
    }
    .feat h3{margin:0 0 6px; font-size:18px}
    .feat p{margin:0; color:var(--muted); font-size:15px}
    .gallery{
      grid-template-columns: repeat(2, 1fr);
      margin-top:14px;
    }
    @media (max-width: 900px){
      .gallery{grid-template-columns: 1fr;}
    }
    .gallery .card{padding:12px}
    .gallery img{border-radius:16px}
    .pricing{
      grid-template-columns: 1fr 1fr;
      align-items:stretch;
      margin-top:14px;
    }
    @media (max-width: 900px){
      .pricing{grid-template-columns: 1fr;}
    }
    .priceBox{padding:18px}
    .price{
      font-size:42px; font-weight:900; margin:8px 0 6px;
    }
    .list{margin:12px 0 0; padding:0 18px 0 0; color:var(--muted)}
    .list li{margin:6px 0}
    .form{
      padding:18px;
      display:grid;
      gap:10px;
    }
    label{font-size:14px; color:var(--muted)}
    input, textarea{
      width:100%;
      padding:12px 12px;
      border-radius:14px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.04);
      color: var(--text);
      outline:none;
      font-family:var(--font);
    }
    textarea{min-height:96px; resize:vertical}
    .fine{font-size:12px; color:var(--muted)}
    footer{
      margin-top:26px;
      color: var(--muted);
      font-size:13px;
      text-align:center;
      padding-top: 10px;
    }

    /* WhatsApp floating button */
    .wa-float{
      position: fixed;
      inset-inline-start: 16px;
      bottom: 16px;
      z-index: 9999;
      display:flex;
      gap:10px;
      align-items:center;
    }
    .wa-btn{
      display:flex; align-items:center; gap:10px;
      padding:12px 14px;
      border-radius:999px;
      background: #25D366;
      color: #06230f;
      font-weight:900;
      text-decoration:none;
      box-shadow: 0 18px 50px rgba(37,211,102,.25);
      border: 0;
      transition: transform .15s ease;
      white-space:nowrap;
    }
    .wa-btn:hover{transform: translateY(-1px)}
    .wa-mini{
      display:none;
      padding:10px 12px;
      border-radius:999px;
      border:1px solid var(--line);
      background: rgba(15,26,45,.75);
      color: var(--text);
      font-weight:700;
      text-decoration:none;
    }
    @media (max-width: 520px){
      .wa-mini{display:block}
      .wa-btn span.txt{display:none}
    }
  </style>
</head>

<body>
  <div class="wrap">
    <header class="nav">
      <div class="brand">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <div style="font-size:16px;">متتبع العادات الذكي</div>
          <div style="font-size:12px;color:var(--muted);margin-top:2px;">Excel & Google Sheets</div>
        </div>
      </div>

      <a class="btn" href="#order">اطلب الآن</a>
    </header>

    <!-- HERO -->
    <section class="grid hero">
      <div>
        <div class="kicker">✅ <b>Smart Habit Tracker</b> • لوحة تحكم ورسوم تلقائية</div>
        <h1>حوّل عاداتك لإنجازات خلال 30 يومًا — بشكل واضح ومحفّز.</h1>
        <p class="sub">
          قالب احترافي لـ <b>Excel</b> و<b>Google Sheets</b> لتتبع العادات اليومية/الأسبوعية،
          مع إحصائيات تلقائية، ستريك، ونظرة كاملة على تقدمك.
        </p>

        <div class="ctaRow">
          <a class="btn primary" id="waTop" href="#">تواصل واتساب للطلب</a>
          <a class="btn" href="#gallery">شاهد الصور</a>
          <a class="btn" href="#features">المميزات</a>
        </div>

        <div class="pillRow">
          <div class="pill">📈 رسوم تلقائية</div>
          <div class="pill">🔥 تتبع الستريك</div>
          <div class="pill">🎯 أهداف شهرية</div>
          <div class="pill">🌙 Dark Mode</div>
        </div>
      </div>

      <div class="card media">
        <!-- HERO IMAGE (بدّل المسار) -->
        <img src="qaidiiiii.jpg" alt="Habit Tracker Dashboard" />
      </div>
    </section>

    <!-- FEATURES -->
    <section class="section" id="features">
      <h2>ماذا ستحصل عليه؟</h2>
      <p>كل شيء جاهز للاستخدام… فقط اكتب عاداتك وابدأ التتبع.</p>

      <div class="grid features">
        <div class="card feat">
          <div class="icon">📊</div>
          <h3>رسوم وإحصائيات تلقائية</h3>
          <p>لوحات تقدم يومي/أسبوعي وشهري تُحدّث تلقائيًا بمجرد وضع العلامات.</p>
        </div>

        <div class="card feat">
          <div class="icon">🔥</div>
          <h3>Streak Tracking</h3>
          <p>تابع سلسلة الالتزام (ستريك) لتحافظ على الحماس والانضباط.</p>
        </div>

        <div class="card feat">
          <div class="icon">🎨</div>
          <h3>حالة ملوّنة وواجهة أنيقة</h3>
          <p>مؤشرات بصرية (Done / Skipped) + تصميم مريح للعين (Dark Mode).</p>
        </div>
      </div>
    </section>

    <!-- GALLERY -->
    <section class="section" id="gallery">
      <h2>صور المنتج</h2>

      <div class="grid gallery">
        <div class="card">
          <img src="qaidi12345.jpg" alt="Habit Tracker - Overview"/>
        </div>
        <div class="card">
          <img src="habitaaaa.jpg" alt="Smart Features" />
        </div>
        <div class="card">
          <img src="kmma.jpg" alt="Perfect For Students" />
        </div>
        <div class="card">
          <img src="Dashboard Templates_ Sales Dashboard.jpg" alt="Dashboard Dark Mode" />
        <div class="card">
<img src="2025 Habit Tracker Spreadsheet Template for Google Sheets, Tracker Template.jpg"  width="300" height="300">
        </div>
        </div>
      </div>
    </section>

    <!-- PRICING + ORDER -->
    <section class="section" id="order">
      <h2>اطلب الآن</h2>
      <p>اختر الطريقة الأنسب: تواصل واتساب مباشرة أو اترك بياناتك وسنتواصل معك.</p>

      <div class="grid pricing">
        <div class="card priceBox">
          <div class="kicker">🎁 تحميل فوري • استخدام غير محدود</div>
          <div class="price">سعر خاص</div>
          <div style="color:var(--muted);margin-top:-2px;">
             <h2>  درهم 49    \5$ </h2>
          </div>

          <ul class="list">
            <li>يدعم Excel و Google Sheets</li>
            <li>تتبع حتى 30 عادة يومية + 15 أسبوعية</li>
            <li>لوحة تحكم + رسوم تلقائية</li>
            <li>Dark Mode + تصميم احترافي</li>
            <li>شراء مرة واحدة واستخدام دائم</li>
          </ul>

          <div class="ctaRow" style="margin-top:16px;">
            <a class="btn primary" id="waMid" href="#">اطلب عبر واتساب</a>
            <a class="btn" href="#faq">أسئلة شائعة</a>
          </div>

          <div class="fine" style="margin-top:10px;">
            * بعد الدفع يتم إرسال الملف مباشرة (أو حسب طريقتك أنت).
          </div>
        </div>

        <div class="card form">
          <div style="font-weight:900; font-size:18px;">نموذج طلب سريع</div>

          <div>
            <label>الاسم</label>
            <input id="name" type="text" placeholder="اكتب اسمك" />
          </div>

          <div>
            <label>رقم واتساب</label>
            <input id="phone" type="tel" placeholder="+212..." />
          </div>

          <div>
            <label>ملاحظة (اختياري)</label>
            <textarea id="note" placeholder="مثال: أريد النسخة الخاصة بـ Google Sheets"></textarea>
          </div>

          <button class="btn primary" id="sendWA" type="button">إرسال الطلب إلى واتساب</button>
          <div class="fine">بالضغط سيتم فتح واتساب برسالة جاهزة تحتوي بياناتك.</div>
        </div>
      </div>
    </section>

    <!-- FAQ -->
    <section class="section" id="faq">
      <h2>أسئلة شائعة</h2>
      <div class="grid features" style="grid-template-columns:repeat(2,1fr)">
        <div class="card feat">
          <h3>هل يعمل على الهاتف؟</h3>
          <p>الأفضل على الكمبيوتر، ويمكن فتحه على الهاتف عبر Google Sheets (قد تكون التجربة أقل راحة).</p>
        </div>
        <div class="card feat">
          <h3>كيف أبدأ؟</h3>
          <p>تكتب عاداتك، ثم كل يوم تختار Done/Skipped أو تضع علامة، والباقي يتم تلقائيًا.</p>
        </div>
        <div class="card feat">
          <h3>هل يمكنني استخدامه كل شهر؟</h3>
          <p>نعم. يمكنك تكرار التبويب لشهر جديد (Unlimited Use).</p>
        </div>
        <div class="card feat">
          <h3>هل يتوفر شرح؟</h3>
          <p>بطبع تتوصل بشرح مع المنتج.</p>
        </div>
      </div>
    </section>

    <footer>
      © <span id="year"></span> — متتبع العادات الذكي • تواصل واتساب للطلب
    </footer>
  </div>

  <!-- Floating WhatsApp -->
  <div class="wa-float">
    <a class="wa-btn" id="waFloat" href="#">
      <span style="font-size:18px">💬</span>
      <span class="txt">واتساب: تواصل للطلب الآن</span>
    </a>
    <a class="wa-mini" href="#order">اطلب</a>
  </div>

  <script>
    // ========= إعدادات واتساب =========
    // ضع رقمك بصيغة دولية بدون + وبدون مسافات
    // مثال المغرب: 2126XXXXXXXX
    const WHATSAPP_NUMBER = "0701076318"; // <-- غيّر الرقم هنا

    const defaultMessage =
      "سلام! بغيت نطلب Smart Habit Tracker (Excel/Google Sheets). واش متوفر دابا؟";

    function waLink(message){
      const text = encodeURIComponent(message);
      return `https://wa.me/${WHATSAPP_NUMBER}?text=${text}`;
    }

    // Buttons links
    const waTop   = document.getElementById("waTop");
    const waMid   = document.getElementById("waMid");
    const waFloat = document.getElementById("waFloat");

    [waTop, waMid, waFloat].forEach(el => el.href = waLink(defaultMessage));

    // Form to WhatsApp
    document.getElementById("sendWA").addEventListener("click", () => {
      const name  = document.getElementById("name").value.trim() || "بدون اسم";
      const phone = document.getElementById("phone").value.trim() || "غير مذكور";
      const note  = document.getElementById("note").value.trim() || "لا يوجد";

      const msg =
`طلب جديد 🧾
المنتج: Smart Habit Tracker
الاسم: ${name}
واتساب: ${phone}
ملاحظة: ${note}

ممكن تفاصيل الدفع/التسليم؟`;

      window.open(waLink(msg), "_blank");
    });

    document.getElementById("year").textContent = new Date().getFullYear();
  </script>
</body>
</html>
