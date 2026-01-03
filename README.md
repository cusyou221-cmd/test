<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <title>我的第一個網頁產生器</title>
    <style>
        body { font-family: sans-serif; text-align: center; background: #222; color: white; }
        canvas { border: 2px solid #555; background: #000; margin-top: 20px; }
        button { padding: 10px 20px; font-size: 16px; cursor: pointer; background: skyblue; border: none; border-radius: 5px; }
        button:hover { background: lightblue; }
    </style>
</head>
<body>

    <h1>點擊按鈕產生隨機星空</h1>
    <button onclick="drawArt()">開始繪製</button>
    <br>
    <canvas id="myCanvas" width="800" height="500"></canvas>

    <script>
        function drawArt() {
            const canvas = document.getElementById('myCanvas');
            const ctx = canvas.getContext('2d');
            
            // 清除上次畫的內容
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // 修正後的迴圈：使用 let 避免衝突，並畫出 5000 個點
            for (let i = 0; i < 50; i++) {
                for (let j = 0; j < 100; j++) {
                    ctx.fillStyle = 'skyblue';
                    let x = Math.random() * canvas.width;
                    let y = Math.random() * canvas.height;
                    ctx.fillRect(x, y, 2, 2);
                }
            }
        }
    </script>
</body>
</html>
