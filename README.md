<!doctype html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>صفحة تسجيل الدخول - منصّة الإمام الصادق</title>

  <style>
    /* CSS Variables */
    :root {
      --primary-color: #0ea5e9;
      --primary-hover-color: #38bdf8;
      --secondary-color: #e0f2fe;
      --text-color: #0f172a;
      --muted-text-color: #475569;
      --white-color: #ffffff;
      --border-color: #e0f2fe;
      --shadow-color: rgba(14, 165, 233, .25);
      --radius: 16px;
      --focus-shadow: 0 0 0 3px rgba(14, 165, 233, .35);
    }

    /* General Styles */
    * {
      box-sizing: border-box;
    }
    html, body {
      height: 100%;
      margin: 0;
    }
    body {
      font-family: system-ui, -apple-system, Segoe UI, Roboto, "Noto Naskh Arabic", "Noto Sans Arabic", Arial, sans-serif;
      color: var(--text-color);
      background: radial-gradient(1200px 500px at 80% -10%, var(--primary-hover-color), transparent 60%),
                  radial-gradient(900px 400px at 10% 110%, var(--secondary-color), transparent 60%),
                  linear-gradient(180deg, #f0f9ff, var(--white-color));
      display: grid;
      place-items: center;
      padding: 24px;
    }

    /* Card Component */
    .card {
      width: 100%;
      max-width: 420px;
      background: var(--white-color);
      border-radius: var(--radius);
      box-shadow: 0 10px 30px var(--shadow-color);
      overflow: hidden;
      border: 1px solid var(--border-color);
    }

    /* Header */
    .header {
      padding: 28px 28px 12px;
    }
    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .logo-img {
      width: 60px;
      height: 60px;
      border-radius: 50%;
      background: #fff;
      padding: 6px;
      object-fit: cover;
      box-shadow: 0 0 8px rgba(0, 0, 0, 0.1);
    }
    h1 {
      margin: 6px 0 0;
      font-size: clamp(20px, 2.5vw, 24px);
    }
    .sub {
      margin: 8px 0 0;
      color: var(--muted-text-color);
      font-size: 14px;
    }

    /* Form Styles */
    form {
      padding: 20px 28px 28px;
    }
    .field {
      margin-top: 16px;
    }
    label {
      display: block;
      font-size: 14px;
      margin-bottom: 8px;
      color: var(--muted-text-color);
    }
    .control {
      position: relative;
    }
    input {
      width: 100%;
      padding: 14px 44px 14px 14px;
      border: 1px solid var(--border-color);
      border-radius: 12px;
      background: #fff;
      outline: none;
      font-size: 16px;
      transition: box-shadow .15s, border-color .15s, transform .02s;
    }
    input:focus {
      border-color: var(--primary-hover-color);
      box-shadow: var(--focus-shadow);
    }
    input:active {
      transform: translateY(0.5px);
    }

    /* Password Toggle Button */
    .toggle {
      position: absolute;
      inset-inline-start: 12px;
      inset-block: 0;
      display: grid;
      place-items: center;
      width: 28px;
      cursor: pointer;
      user-select: none;
      border: none;
      background: transparent;
      padding: 0;
      margin: 0;
      outline: none;
    }

    /* Form Actions and Buttons */
    .actions {
      display: flex;
      gap: 12px;
      margin-top: 22px;
      align-items: center;
    }
    .btn {
      flex: 1;
      border: none;
      cursor: pointer;
      border-radius: 12px;
      padding: 14px 16px;
      font-size: 16px;
      font-weight: 700;
      transition: filter .15s, transform .04s, box-shadow .15s;
    }
    .btn-primary {
      background: linear-gradient(180deg, var(--primary-hover-color), var(--primary-color));
      color: var(--white-color);
      box-shadow: 0 8px 18px rgba(14, 165, 233, .35);
    }
    .btn-primary:hover {
      filter: brightness(1.03);
    }
    .btn-primary:active {
      transform: translateY(1px);
    }
    .btn-ghost {
      background: #f8fbff;
      color: var(--primary-color);
      border: 1px solid var(--border-color);
    }

    /* Footer */
    .footer {
      padding: 16px 28px 26px;
      border-top: 1px dashed var(--border-color);
      background: linear-gradient(0deg, #f0f9ff, #fff 40%);
      font-size: 13px;
      color: var(--muted-text-color);
      text-align: center;
    }

    /* Validation and Error Messages */
    .error {
      display: none;
      margin-top: 8px;
      font-size: 13px;
      color: #b91c1c;
    }
    .field.invalid input {
      border-color: #fda4a4;
    }
    .field.invalid .error {
      display: block;
    }

    /* Animation Optimization */
    @media (prefers-reduced-motion: reduce) {
      * {
        transition: none !important;
      }
    }
  </style>
</head>
<body>
  <main class="card" role="main" aria-labelledby="title">
    <div class="header">
      <div class="brand">
        <img src="imam-sadiq-logo.png" alt="شعار جامعة الإمام الصادق" class="logo-img" />
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
      ليس لديك حساب؟ <a href="#" style="color:var(--primary-color); text-decoration:none;">إنشاء حساب</a>
    </div>
  </main>

  <script>
    function togglePassword() {
      const input = document.getElementById('password');
      input.type = input.type === 'password' ? 'text' : 'password';
    }

    function clearErrors() {
      document.getElementById('userField').classList.remove('invalid');
      document.getElementById('passField').classList.remove('invalid');
    }

    document.getElementById('loginForm').addEventListener('submit', function(e) {
      e.preventDefault();
      clearErrors();

      const user = document.getElementById('username');
      const pass = document.getElementById('password');

      let isValid = true;
      if (!user.value || user.value.trim().length < 3) {
        document.getElementById('userField').classList.add('invalid');
        isValid = false;
      }
      if (!pass.value || pass.value.length < 6) {
        document.getElementById('passField').classList.add('invalid');
        isValid = false;
      }

      if (isValid) {
        alert('تم التحقق من المدخلات ✅ (اربطه بواجهتك الخلفية)');
      }
    });
  </script>
</body>
</html>
