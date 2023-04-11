```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CROS</title>
  <!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">

</head>

<body>
  <div class="container">
    <h2 class="page-header">jquery-jsonp</h2>
    <button class="btn btn-primary">点击发送请求</button>
  </div>

  <script>
    const btn = document.querySelector('button');

    btn.onclick = function () {
      //创建对象
      const xhr = new XMLHttpRequest();
      //初始化设置
      xhr.open('GET', 'http://127.0.0.1:8000/cors-server');
      //发送
      xhr.send();
      //绑定事件
      xhr.onreadystatechange = function () {
        if (xhr.readyState === 4) {
          if (xhr.status >= 200 && xhr.status < 300) {
            //输出响应体
            console.log(xhr.response);
          }
        }
      }
    }
  </script>
</body>






</html>
```
