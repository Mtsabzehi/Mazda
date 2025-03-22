<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        .error-message {
            color: red;
            font-size: 1rem;
            text-align: center;
            margin-top: 15px;
            padding: 8px;
            border-radius: 4px;
            background: #000000;
            display: none;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: url('https://biaupload.com/do.php?imgf=org-8323b74512921.jpg') no-repeat center center fixed;
            background-size: cover;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }
        .login-container {
            background: #000000d7;
            padding: 40px 50px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            width: 100%;
            max-width: 450px;
            animation: fadeIn 0.5s ease-in-out;
            z-index: 1;
        }
        .login-header {
            text-align: center;
            margin-bottom: 25px;
        }
        .page-logo {
            max-width: 200px;
            width: 100%;
            height: auto;
            margin: 0 auto 20px auto;
            display: block;
        }
        .form-group input {
            width: 100%;
            padding: 12px 20px;
            border: 2px solid #000000;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s ease;
        }
        .form-group input:focus {
            border-color: #bbb369;
            outline: none;
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }
        .login-btn {
            background: linear-gradient(135deg, #bbb369 0%, #bbb369 100%);
            color: white;
            padding: 14px 0;
            border: none;
            border-radius: 8px;
            width: 100%;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
        }
        .login-btn:hover {
            background: linear-gradient(135deg, #bbb369 0%, #000000 100%);
        }
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>
</head>
<body>
    <div class="login-container">
        <div class="login-header">
            <img src="https://biaupload.com/do.php?imgf=org-266e94ba85261.png" alt="Logo" class="page-logo">
            <b style="color: #bbb369;"><h1>Welcome Back</h1></b>
            <b style="color: #bbb369;"><h2>Please Login To Your Account</h2></b>
        </div>
        <form id="loginForm">
            <div class="form-group">
                <input type="text" id="username" placeholder="Username" required>
            </div>
            <div class="form-group">
                <input type="password" id="password" placeholder="Password" required>
            </div>
            <button type="submit" class="login-btn">Login</button>
            <div id="error-message" class="error-message"></div>
        </form>
    </div>
    <script>
        // Login Validation
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const username = document.getElementById('username').value.trim();
            const password = document.getElementById('password').value.trim();
            const errorDiv = document.getElementById('error-message');
            if (username === 'Ahoora' && password === 'Mazda') {
                window.location.href = 'https://www.google.com';
            } else {
                errorDiv.textContent = 'The Username or Password is Incorrect. Try again!';
                errorDiv.style.display = 'block';
                setTimeout(() => {
                    errorDiv.style.display = 'none';
                }, 3000);
            }
        });
    </script>
</body>
</html>
