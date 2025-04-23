from flask import Flask, render_template_string

app = Flask(__name__)


@app.route('/')
def confession():
    confession_text = "你就像夜空中最亮的星，照亮了我整个世界。我喜欢你，希望能和你在一起，共度每一个美好的瞬间。"
    html_template = """
<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>表白</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }

       .confession-box {
            background-color: #fff;
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
        }

       .confession-text {
            font-size: 24px;
            color: #333;
            margin-bottom: 20px;
        }

       .btn {
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            font-size: 18px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

       .btn-yes {
            background-color: #28a745;
            color: white;
            margin-right: 10px;
        }

       .btn-yes:hover {
            background-color: #218838;
        }

       .btn-no {
            background-color: #dc3545;
            color: white;
        }

       .btn-no:hover {
            background-color: #c82333;
        }
    </style>
    <script>
        function handleYes() {
            alert('太开心啦，我会好好爱你的！');
        }

        function handleNo() {
            alert('没关系，我会一直等你考虑好的。');
        }
    </script>
</head>

<body>
    <div class="confession-box">
        <p class="confession-text">{{ confession_text }}</p>
        <button class="btn btn-yes" onclick="handleYes()">我愿意</button>
        <button class="btn btn-no" onclick="handleNo()">再考虑</button>
    </div>
</body>

</html>
    """
    return render_template_string(html_template, confession_text=confession_text)


if __name__ == '__main__':
    app.run(debug=True)
    
