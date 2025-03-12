<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Welcome to My Website</h1>
    <input type="file" id="upload" accept="image/*">
    <img id="preview" src="" alt="Your Image">
    <script src="script.js"></script>
</body>
</html># Limon
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 20px;
}

img {
    max-width: 100%;
    height: auto;
    margin-top: 20px;
}
document.getElementById('upload').addEventListener('change', function(event) {
    const file = event.target.files[0];
    if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
            document.getElementById('preview').src = e.target.result;
        };
        reader.readAsDataURL(file);
    }
});
