```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>fetch发送ajax请求</title>
  <!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">
  <script src="https://cdn.bootcdn.net/ajax/libs/axios/1.3.5/axios.js" crossorigin="anonymous"></script>
</head>

<body>
  <div class="container">
    <h2 class="page-header">fetch发送ajax请求</h2>
    <button class="btn btn-info">AJAX</button>
  </div>
</body>

</html>

<script>
  const btn = document.querySelector('button');

  btn.onclick = function () {
    fetch('http://127.0.0.1:8000/fetch-server?vip=10', {
      //请求方法
      method: 'POST',
      //请求头
      headers: {
        name: 'xiaokang'
      },
      //请求体
      body: 'username=admin&password=admin'
    }).then(res => {
      return res.json();
    }).then(req => {
      console.log(req);
    });
  }

</script>
```
