
from flask import Flask, render_template_string

app = Flask(_name_)

# بيانات الكتب
books = [
    {"title": "كتاب 1", "author": "المؤلف الأول", "description": "وصف الكتاب الأول", "image": "https://via.placeholder.com/150"},
    {"title": "كتاب 2", "author": "المؤلف الثاني", "description": "وصف الكتاب الثاني", "image": "https://via.placeholder.com/150"},
    {"title": "كتاب 3", "author": "المؤلف الثالث", "description": "وصف الكتاب الثالث", "image": "https://via.placeholder.com/150"}
]

html_template = """
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مكتبة إلكترونية</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #1E90FF; /* خلفية زرقاء باردة */
            margin: 0;
            padding: 0;
            color: white;
        }
        h1 {
            padding: 20px;
        }
        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }
        .image-container img {
            width: 50%;
            max-width: 400px;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
        }
        .book-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            padding: 20px;
        }
        .book {
            background: white;
            color: black;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            width: 250px;
            text-align: center;
        }
        .book img {
            width: 100%;
            border-radius: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>مرحبًا بكم في المكتبة الإلكترونية</h1>
        <div class="image-container">
            <img src="https://via.placeholder.com/400" alt="صورة">
        </div>
        <div class="book-list">
            {% for book in books %}
            <div class="book">
                <img src="{https://github.com/mainmn/moh-book/blob/main/1719141509237.jpg}}" alt="صورة الكتاب">
                <h2>{{ book.title }}</h2>
                <p><strong>المؤلف:</strong> {{ book.author }}</p>
                <p>{{ book.description }}</p>
            </div>
            {% endfor %}
        </div>
    </div>
</body>
</html>
"""

@app.route('/')
def home():
    return render_template_string(html_template, books=books)

if _name_ == "_main_":
    app.run(debug=True)
https://github.com/mainmn/moh-book/blob/main/1719141509237.jpg
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عرض الصورة</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 20px;
        }
        img {
            max-width: 80%;
            height: auto;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
    </style>
</head>
<body>
    <h1>مرحبًا بك في صفحة عرض الصورة</h1>
    <img src="images/your-image.jpg" alt="وصف الصورة">
</body>
</html>
