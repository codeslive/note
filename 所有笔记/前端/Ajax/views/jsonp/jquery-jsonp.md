```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>jquery-jsonp</title>
  <!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">
  <script src="https://cdn.bootcdn.net/ajax/libs/jquery/3.6.4/jquery.min.js" crossorigin="anonymous"></script>

</head>
<style>
  #result {
    width: 300px;
    height: 200px;
    border: 1px solid sandybrown;
    margin-top: 5px;
  }
</style>


<body>
  <div class="container">
    <h2 class="page-header">jquery-jsonp</h2>
    <button class="btn btn-primary">点击获取用户数据</button>
    <div id="result"></div>
  </div>

  <script>
    $('button').eq(0).click(function () {
      $.getJSON('http://127.0.0.1:8000/jquery-jsonp-server?callback=?', function (data) {
        $('#result').html(`
            名称：${data.name}<br>
            校区：${data.city}
          `)
      });
    });
  </script>
</body>






</html>
```
