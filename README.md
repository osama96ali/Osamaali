<!DOCTYPE html>
<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>تسجيل الدخول</title>
  <style>
    :root{
      --sky-50:#f0f9ff;
      --sky-100:#e0f2fe;
      --sky-200:#bae6fd;
      --sky-300:#7dd3fc;
      --sky-400:#38bdf8;
      --sky-500:#0ea5e9;
      --text:#0f172a;
      --muted:#475569;
      --white:#ffffff;
      --radius:16px;
      --shadow: 0 10px 30px rgba(14,165,233,.25);
      --focus: 0 0 0 3px rgba(14,165,233,.35);
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: system-ui, -apple-system, Segoe UI, Roboto, "Noto Naskh Arabic","Noto Sans Arabic", Arial, sans-serif;
      color:var(--text);
      background:
        radial-gradient(1200px 500px at 80% -10%, var(--sky-200), transparent 60%),
        radial-gradient(900px 400px at 10% 110%, var(--sky-100), transparent 60%),
        linear-gradient(180deg, var(--sky-50), var(--white));
      display:grid;
      place-items:center;
      padding:24px;
    }

    .card{
      width:100%;
      max-width: 420px;
      background: var(--white);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow:hidden;
      border:1px solid var(--sky-100);
    }

    .header{
      padding: 28px 28px 12px;
    }
    .brand{
      display:flex;
      align-items:center;
      gap:12px;
    }
    .logo-img{
      width:60px;
      height:60px;
      border-radius:50%;
      background:#fff;
      padding:6px;
      object-fit:cover;
      box-shadow:0 0 8px rgba(0,0,0,0.1);
    }
    h1{
      margin:6px 0 0; font-size: clamp(20px, 2.5vw, 24px);
    }
    .sub{
      margin:8px 0 0; color:var(--muted); font-size:14px;
    }

    form{ padding: 20px 28px 28px; }

    .field{
      margin-top:16px;
    }
    label{
      display:block; font-size:14px; margin-bottom:8px; color:var(--muted);
    }
    .control{
      position:relative;
    }
    input{
      width:100%;
      padding: 14px 44px 14px 14px;
      border: 1px solid var(--sky-200);
      border-radius:12px;
      background:#fff;
      outline:none;
      font-size:16px;
      transition: box-shadow .15s, border-color .15s, transform .02s;
    }
    input:focus{
      border-color: var(--sky-400);
      box-shadow: var(--focus);
    }
    input:active{ transform: translateY(0.5px); }

    .toggle{
      position:absolute; inset-inline-start:12px; inset-block:0;
      display:grid; place-items:center; width:28px;
      cursor:pointer; user-select:none; border:none; background:transparent;
      padding:0; margin:0; outline:none;
    }

    .hint{
      margin-top:8px; font-size:12px; color:var(--muted);
    }

    .actions{
      display:flex; gap:12px; margin-top:22px; align-items:center;
    }
    .btn{
      flex:1;
      border:none; cursor:pointer; border-radius:12px;
      padding:14px 16px; font-size:16px; font-weight:700;
      transition: filter .15s, transform .04s, box-shadow .15s;
    }
    .btn-primary{
      background: linear-gradient(180deg, var(--sky-400), var(--sky-500));
      color:#fff; box-shadow: 0 8px 18px rgba(14,165,233,.35);
    }
    .btn-primary:hover{ filter: brightness(1.03); }
    .btn-primary:active{ transform: translateY(1px); }

    .btn-ghost{
      background: #f8fbff;
      color: var(--sky-500);
      border: 1px solid var(--sky-200);
    }

    .footer{
      padding: 16px 28px 26px;
      border-top:1px dashed var(--sky-100);
      background: linear-gradient(0deg, var(--sky-50), #fff 40%);
      font-size:13px; color:var(--muted); text-align:center;
    }

    .error{
      display:none; margin-top:8px; font-size:13px; color:#b91c1c;
    }
    .field.invalid input{ border-color:#fda4a4; }
    .field.invalid .error{ display:block; }

    @media (prefers-reduced-motion: reduce){
      *{transition:none !important}
    }
  </style>
</head>
<body>
  <main class="card" role="main" aria-labelledby="title">
    <div class="header">
      <div class="brand">
        <!-- شعارك الجديد -->
        <img src="logo2.jpg" alt="شعار" class="logo-img" />
        <div style="font-weight:700">منصّتك</div>
      </div>
      <h1 id="title">تسجيل الدخول</h1>
      <p class="sub">يرجى إدخال اسم المستخدم وكلمة المرور للمتابعة.</p>
    </div>

    <form id="loginForm" novalidate>
      <div class="field" id="userField">
        <label for="username">اسم المستخدم</label>
        <div class="control">
          <input id="username" name="username" type="text"
                 inputmode="text" autocomplete="username"
                 placeholder="example_user" required minlength="3" />
        </div>
        <div class="error" aria-live="polite">الرجاء إدخال اسم مستخدم صالح (٣ أحرف فأكثر).</div>
      </div>

      <div class="field" id="passField">
        <label for="password">كلمة المرور</label>
        <div class="control">
          <input id="password" name="password" type="password"
                 autocomplete="current-password"
                 placeholder="••••••••" required minlength="6" />
          <button class="toggle" type="button" aria-label="إظهار أو إخفاء كلمة المرور" title="إظهار/إخفاء"
                  onclick="togglePassword()">
            👁️
          </button>
        </div>
        <div class="hint">يجب أن تكون ٦ أحرف على الأقل.</div>
        <div class="error" aria-live="polite">الرجاء إدخال كلمة مرور أطول.</div>
      </div>

      <div class="actions">
        <button class="btn btn-ghost" type="reset" onclick="clearErrors()">مسح</button>
        <button class="btn btn-primary" type="submit">دخول</button>
      </div>
    </form>

    <div class="footer">
      ليس لديك حساب؟ <a href="#" style="color:var(--sky-500); text-decoration:none;">إنشاء حساب</a>
    </div>
  </main>

  <script>
    function togglePassword(){
      const input = document.getElementById('password');
      input.type = input.type === 'password' ? 'text' : 'password';
    }

    function clearErrors(){
      document.getElementById('userField').classList.remove('invalid');
      document.getElementById('passField').classList.remove('invalid');
    }

    document.getElementById('loginForm').addEventListener('submit', function(e){
      e.preventDefault();
      clearErrors();

      const user = document.getElementById('username');
      const pass = document.getElementById('password');

      let ok = true;
      if(!user.value || user.value.trim().length < 3){
        document.getElementById('userField').classList.add('invalid');
        ok = false;
      }
      if(!pass.value || pass.value.length < 6){
        document.getElementById('passField').classList.add('invalid');
        ok = false;
      }

      if(ok){
        alert('تم التحقق من المدخلات ✅ (اربطه بواجهتك الخلفيه)');
      }
    });
  </script>
</body>
</html>