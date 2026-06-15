# index.-html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Halaman Login Kadori</title>
    <style>
        /* --- CSS untuk Desain Tampilan --- */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

        .login-container {
            background: #fff;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
            width: 350px;
        }

        .login-container h2 {
            text-align: center;
            margin-bottom: 24px;
            color: #2a5298;
        }

        .input-group {
            margin-bottom: 15px;
        }

        .input-group label {
            display: block;
            margin-bottom: 5px;
            color: #666;
            font-size: 14px;
        }

        .input-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
            box-sizing: border-box;
            font-size: 14px;
        }

        .input-group input:focus {
            border-color: #2a5298;
            outline: none;
        }

        button {
            width: 100%;
            padding: 12px;
            background-color: #2a5298;
            border: none;
            border-radius: 6px;
            color: white;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
        }

        button:hover {
            background-color: #1e3c72;
        }

        .message {
            margin-top: 15px;
            text-align: center;
            font-size: 14px;
            font-weight: bold;
        }
        
        .success { color: #2ecc71; }
        .error { color: #e74c3c; }
    </style>
</head>
<body>

    <div class="login-container">
        <h2>Masuk Akun</h2>
        <form id="loginForm">
            <div class="input-group">
                <label for="username">Username</label>
                <input type="text" id="username" required placeholder="Masukkan username">
            </div>
            <div class="input-group">
                <label for="password">Password</label>
                <input type="password" id="password" required placeholder="Masukkan password">
            </div>
            <button type="submit">Login</button>
        </form>
        <div id="message" class="message"></div>
    </div>

    <script>
        const loginForm = document.getElementById('loginForm');
        const usernameInput = document.getElementById('username');
        const passwordInput = document.getElementById('password');
        const messageDiv = document.getElementById('message');

        loginForm.addEventListener('submit', function(event) {
            // Mencegah browser reload halaman saat tombol ditekan
            event.preventDefault(); 

            // Mengambil input dari user
            const username = usernameInput.value;
            const password = passwordInput.value;

            // Logika pengecekan dengan akun baru Anda
            if (username === 'kadori bersayap' && password === 'Kadori123') {
                // Jika data yang dimasukkan BENAR
                messageDiv.textContent = "Login Berhasil! Selamat datang Kadori Bersayap.";
                messageDiv.className = "message success";
                
                // (Opsional) Bersihkan form setelah sukses
                loginForm.reset();
            } else {
                // Jika data yang dimasukkan SALAH
                messageDiv.textContent = "Username atau Password salah! Silakan coba lagi.";
                messageDiv.className = "message error";
            }
        });
    </script>

</body>
</html>
