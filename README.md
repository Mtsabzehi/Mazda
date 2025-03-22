<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        /* Error Message Style */
        .error-message {
            color: #bbb369;
            font-size: 0.9rem;
            text-align: center;
            margin: 15px 0;
            padding: 8px;
            border-radius: 4px;
            background: #000000;
            display: none;
        }

        /* General Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: url('https://biaupload.com/do.php?imgf=org-0e9bcbfdaed91.jpg') no-repeat center center fixed;
            background-size: cover;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        /* Security Message Box */
        #overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        .message-box {
            background: #000000e1;
            border-radius: 12px;
            padding: 30px;
            max-width: 400px;
            width: 90%;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.15);
            text-align: center;
            animation: slideIn 3s ease-out;
        }

        .message-box h2 {
            color: #e74c3c;
            font-size: 1.8rem;
            margin-bottom: 15px;
        }

        .message-box p {
            color: #333;
            font-size: 1.1rem;
            margin-bottom: 25px;
        }

        .btn-ok {
            background: linear-gradient(135deg, #bbb369 0%, #bbb369 100%);
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.2s ease;
        }

        .btn-ok:hover {
            transform: translateY(-2px);
            background: linear-gradient(135deg, #bbb369 0%, #000000 100%);
        }

        /* Login Container */
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

        .forgot-password {
            display: block;
            text-align: center;
            margin: 20px 0;
            color: #bbb369;
            font-size: 0.9rem;
            transition: color 2s ease;
        }

        .forgot-password:hover {
            color: rgb(0, 0, 0);
        }

        .social-icons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 15px;
        }

        .social-icon {
            background: #bbb369;
            padding: 12px;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .social-icon:hover {
            transform: translateY(-3px);
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

        @keyframes slideIn {
            from {
                transform: translateY(-20px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        /* Responsive Styles */
        @media (max-width: 480px) {
            .login-container {
                padding: 30px;
            }
            
            .page-logo {
                max-width: 180px;
            }
        }
    </style>
</head>
<body>
    <!-- Security Message Overlay -->
    <div id="overlay">
        <div class="message-box">
            <b style="color: #ff0000;"><h1>Attention</h1></b>
            <b style="color: #bbb369;"><h3>Please turn on your VPN</h3></b>
            <button class="btn-ok" onclick="closeMessageBox()">OK</button>
        </div>
    </div>

    <!-- Login Container -->
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
            <a href="#" class="forgot-password">Forgot Password?</a>
            <div id="error-message" class="error-message"></div>
        </form>

        <div class="social-login">
            <p style="color: #bbb369;">Or continue with</p>
            <div class="social-icons">
                <div class="social-icon google">
                    <i class="fab fa-google"></i>
                </div>
                <div class="social-icon facebook">
                    <i class="fab fa-facebook-f"></i>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Security Message Functionality
        function closeMessageBox() {
            document.getElementById('overlay').style.display = 'none';
        }

        document.addEventListener('DOMContentLoaded', () => {
            document.getElementById('overlay').style.display = 'flex';
        });

        // Login Validation
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            const errorDiv = document.getElementById('error-message');

            if(username === 'KMZ' && password === 'Delester') {
                window.location.href = 'https://shop.bodybuilding.com/';
            } else {
                errorDiv.textContent ='The Username or Password is Incorrect. Try again!';
                errorDiv.style.display = 'block';
                
                setTimeout(() => {
                    errorDiv.style.display = 'none';
                }, 3000);
            }
        });
    </script>
</body>
</html>
