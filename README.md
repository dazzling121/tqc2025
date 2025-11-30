<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chơi Game H5</title>
    
    <script>
        // Hàm kiểm tra xem thiết bị có phải là di động không (được giữ lại)
        function isMobileDevice() {
            const userAgent = navigator.userAgent || navigator.vendor || window.opera;
            return /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(userAgent);
        }

        // Logic bảo mật (Giữ nguyên)
        document.addEventListener('contextmenu', e => e.preventDefault());
        document.addEventListener('keydown', e => {
            if (e.key === 'F12' || 
                (e.ctrlKey || e.metaKey) && (e.shiftKey && (e.key === 'I' || e.key === 'J' || e.key === 'C' || e.key === 'K') || e.key === 'U')) 
            {
                e.preventDefault();
            }
        });

        // Phát hiện DevTools (Giữ nguyên)
        const checkDevTools = () => {
            const isDevToolsOpen = (window.outerWidth - window.innerWidth > 100) || (window.outerHeight - window.innerHeight > 100);
            
            if (isDevToolsOpen) {
                document.body.innerHTML = '<h1>Bạn không được phép kiểm tra mã nguồn trang này!</h1>';
            }
        };

        window.onload = function() {
            // Chạy kiểm tra thiết bị và đặt nguồn game (Giữ lại logic, mặc dù không dùng iframe)
            // Bạn có thể dùng isMobileDevice() để tùy chỉnh link ở bước tiếp theo nếu cần
            
            // Logic chuyển focus về body (Giữ nguyên)
            document.body.focus();
            document.addEventListener('mousedown', function() {
                document.body.focus(); 
            });
        };

        setInterval(checkDevTools, 500);
        window.addEventListener('resize', checkDevTools);
    </script>

    <style>
        html, body {
            margin: 0;
            padding: 0;
            width: 100vw;
            height: 100vh;
            overflow: auto; /* Thay đổi thành auto để cuộn nếu cần */
            background-color: #f0f0f0;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center; /* Căn giữa nội dung theo chiều dọc */
            font-family: sans-serif;
            text-align: center;
        }

        h1 {
            color: #333;
            margin: 10px 0 30px; /* Thêm khoảng cách dưới tiêu đề */
            font-size: 1.8em;
        }
        
        .game-link-container {
            padding: 30px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }

        .game-link-button {
            display: inline-block;
            padding: 15px 30px;
            background-color: #007bff; /* Màu xanh dương nổi bật */
            color: white;
            text-decoration: none;
            font-size: 1.5em;
            font-weight: bold;
            border-radius: 8px;
            transition: background-color 0.3s, transform 0.1s;
        }

        .game-link-button:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
        }
    </style>
</head>
<body>

    <h1>🎮 Chơi Game H5 (Không thể nhúng) 🕹️</h1>
    
    <div class="game-link-container">
        <p style="font-size: 1.1em; color: #555;">
            Trò chơi không thể nhúng trực tiếp do vấn đề bảo mật của máy chủ.<br>
            Vui lòng nhấp vào nút dưới đây để chơi game ở **cửa sổ mới**.
        </p>
        
        <a 
            href="http://103.153.74.65:81/?mpc=0" 
            target="_blank" 
            class="game-link-button"
            title="Mở game trong tab mới"
        >
            BẤM ĐỂ CHƠI GAME
        </a>
    </div>

</body>
</html>
