# <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f0f0f0;
        }
        .login-container {
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 300px;
            text-align: center;
        }
        .login-container h2 {
            margin-bottom: 20px;
        }
        .login-container input {
            width: calc(100% - 20px);
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .login-container button {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background: #007bff;
            color: white;
            cursor: pointer;
        }
        .login-container button:hover {
            background: #0056b3;
        }
        .error-message {
            color: red;
            font-size: 0.9em;
        }
    </style>
</head>
<body>
    <div class="login-container">
        <h2>Login</h2>
        <form id="loginForm">
            <input type="email" id="email" placeholder="Email" required>
            <input type="password" id="password" placeholder="Password" required>
            <button type="submit">Login</button>
            <p class="error-message" id="errorMessage" style="display: none;">Invalid email or password.</p>
        </form>
    </div>
    <script>
        document.getElementById('loginForm').addEventListener('submit', function (e) {
            e.preventDefault(); // Prevent form submission
            
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;
            const errorMessage = document.getElementById('errorMessage');
            
            // Admin credentials
            const adminEmail = 'admin@empher.com';
            const adminPassword = 'empher@123';
            
            // User credentials
            const userEmail = 'user@empher.com';
            const userPassword = 'user@123';
            
            // Validate credentials
            if (email === adminEmail && password === adminPassword) {
                alert('Logged in as Admin.');
                localStorage.setItem('loginData', JSON.stringify({ email, role: 'Admin' }));
                window.location.href = 'admin.html';
            } else if (email === userEmail && password === userPassword) {
                localStorage.setItem('loginData', JSON.stringify({ email, role: 'User' }));
                window.location.href = 'books.html';
            } else {
                errorMessage.style.display = 'block';
            }
        });
    </script>  


    
</body>
</html>
