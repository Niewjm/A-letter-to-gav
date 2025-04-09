<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A letter from junmeng</title>
    <style>
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
            background-color: #fff5f7;
        }
        .container {
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 4px 15px rgba(255, 105, 180, 0.1);
            margin-top: 30px;
            border: 1px solid #ffb6c1;
        }
        h2 {
            color: #e75480;
            margin-bottom: 25px;
            font-weight: normal;
        }
        input, textarea {
            padding: 12px;
            margin: 10px 0;
            width: 80%;
            border: 1px solid #ffb6c1;
            border-radius: 8px;
            font-size: 16px;
            background-color: #fff9fa;
        }
        button {
            background-color: #ff69b4;
            color: white;
            border: none;
            padding: 12px 25px;
            font-size: 16px;
            border-radius: 8px;
            cursor: pointer;
            margin-top: 15px;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #e75480;
        }
        #result {
            margin-top: 25px;
            padding: 15px;
            border-radius: 8px;
            display: none;
            font-size: 16px;
        }
        .success {
            background-color: #f8e1e7;
            color: #e75480;
            border: 1px solid #ff69b4;
        }
        .error {
            background-color: #ffebee;
            color: #c62828;
            border: 1px solid #ef5350;
        }
        a {
            color: #e75480;
            text-decoration: none;
            font-weight: bold;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>A letter from junmeng</h2>
        
        <div>
            <p>1. 请输入您的姓名：</p>
            <input type="text" id="nameInput" placeholder="请输入姓名">
        </div>
        
        <div>
            <p>2. 你觉得女生里面谁最好看？</p>
            <textarea id="answerInput" placeholder="请输入你的想法..." rows="4"></textarea>
        </div>
        
        <button onclick="verify()">提交答案</button>
        
        <div id="result"></div>
    </div>

    <script>
        function verify() {
            const name = document.getElementById('nameInput').value.trim().toLowerCase();
            const answer = document.getElementById('answerInput').value.trim();
            const resultDiv = document.getElementById('result');
            
            // 验证姓名
            if (name !== 'gavrielle chin qi eng') {
                resultDiv.innerHTML = "验证失败：请输入正确的姓名";
                resultDiv.className = "error";
                resultDiv.style.display = "block";
                return;
            }
            
            // 发送答案到邮箱
            const emailLink = `mailto:niewjunmeng1111@gmail.com?subject=来自Gavrielle的回答&body=${encodeURIComponent(answer)}`;
            window.location.href = emailLink;
            
            // 显示成功信息
            resultDiv.innerHTML = '感谢你的回答！<br><br>文档链接：<br><a href="https://docs.google.com/document/d/1NOh4DOxOzbx4IfG1_ylB4KfJu79pMXG_NUGRa5gHua8/edit?usp=drivesdk" target="_blank">点击查看信件</a>';
            resultDiv.className = "success";
            resultDiv.style.display = "block";
        }
    </script>
</body>
</html>
