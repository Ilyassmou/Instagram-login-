<!DOCTYPE html>
<html lang="ar">
<head>
  <meta charset="UTF-8">
  <title>Instagram Login</title>
  <style>
    body {
      background-color: #fafafa;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    .login-container {
      background-color: white;
      border: 1px solid #dbdbdb;
      padding: 40px 30px;
      width: 350px;
      text-align: center;
      margin-bottom: 10px;
    }

    .login-container h1 {
      font-family: 'Billabong', cursive;
      font-size: 48px;
      margin-bottom: 30px;
      color: #262626;
    }

    .login-container input {
      width: 100%;
      padding: 10px;
      margin: 5px 0;
      background: #fafafa;
      border: 1px solid #dbdbdb;
      border-radius: 3px;
    }

    .login-container input[type="submit"] {
      background-color: #3897f0;
      color: white;
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
      border: none;
    }

    .login-container .error {
      color: red;
      font-size: 13px;
      margin-top: 10px;
    }

    .links {
      text-align: center;
      font-size: 14px;
      margin-top: 15px;
    }

    .links a {
      color: #3897f0; /* لون أزرق واضح */
      text-decoration: none;
      margin: 5px;
      display: block;
      font-weight: bold;
    }

    .links a:hover {
      text-decoration: underline;
    }

    .signup-box {
      background-color: white;
      border: 1px solid #dbdbdb;
      padding: 20px;
      width: 350px;
      text-align: center;
      font-size: 14px;
    }

    .signup-box a {
      color: #3897f0;
      text-decoration: none;
      font-weight: bold;
    }

    .signup-box a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <div class="login-container">
    <h1>Instagram</h1>
    <form id="loginForm">
      <input type="text" id="email" placeholder="البريد الإلكتروني أو اسم المستخدم" required>
      <input type="password" id="password" placeholder="كلمة المرور" required>
      <div class="error" id="error"></div>
      <input type="submit" value="تسجيل الدخول">
    </form>

    <div class="links">
      <a href="#">هل نسيت كلمة المرور؟</a>
    </div>
  </div>

  <div class="signup-box">
    ليس لديك حساب؟ <a href="#">إنشاء حساب جديد</a>
  </div>

  <script>
    const form = document.getElementById('loginForm');
    const errorDiv = document.getElementById('error');

    form.addEventListener('submit', function(e) {
      e.preventDefault();

      const email = document.getElementById('email').value.trim();
      const password = document.getElementById('password').value;

      let errorMsg = '';

      if (email === '') {
        errorMsg = 'الرجاء إدخال البريد الإلكتروني أو اسم المستخدم.';
      } else if (password.length < 6) {
        errorMsg = 'كلمة المرور يجب أن تكون 6 أحرف على الأقل.';
      }

      if (errorMsg) {
        errorDiv.textContent = errorMsg;
      } else {
        errorDiv.textContent = '';
        alert('تم تسجيل الدخول!');
        form.reset();
      }
    });
  </script>

</body>
</html>
