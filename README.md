<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Student Article Board</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      padding: 20px;
    }
    h1 {
      text-align: center;
    }
    .form-container, .articles-container {
      max-width: 700px;
      margin: 20px auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px #ccc;
    }
    input, textarea {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      font-size: 1rem;
    }
    button {
      margin-top: 10px;
      padding: 10px 20px;
      font-size: 1rem;
      background-color: #0077cc;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .article {
      border-top: 1px solid #ccc;
      padding: 15px 0;
    }
    .article h3 {
      margin-bottom: 5px;
    }
    .article p {
      margin-top: 0;
    }
  </style>
</head>
<body>

  <h1>Student Article Board</h1>

  <div class="form-container">
    <h2>Write an Article</h2>
    <input type="text" id="title" placeholder="Article Title" />
    <textarea id="content" rows="6" placeholder="Write your article here..."></textarea>
    <button onclick="postArticle()">Post Article</button>
  </div>

  <div class="articles-container" id="articles">
    <h2>Published Articles</h2>
    <!-- Articles appear here -->
  </div>

  <script>
    function postArticle() {
      const title = document.getElementById('title').value.trim();
      const content = document.getElementById('content').value.trim();

      if (!title || !content) {
        alert("Please fill out both fields.");
        return;
      }

      const articleBox = document.createElement('div');
      articleBox.className = 'article';
      articleBox.innerHTML = `
        <h3>${title}</h3>
        <p>${content}</p>
      `;

      document.getElementById('articles').appendChild(articleBox);

      // Clear the form
      document.getElementById('title').value = '';
      document.getElementById('content').value = '';
    }
  </script>

</body>
</html>
