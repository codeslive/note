```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>jsonp实现跨域</title>
  <!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">
  <!-- <script src="https://cdn.bootcdn.net/ajax/libs/axios/1.3.5/axios.js" crossorigin="anonymous"></script> -->

</head>
<style>
  #result {
    width: 200px;
    height: 200px;
    border: 1px solid sandybrown;
    line-height: 200px;
    text-align: center;
  }
</style>


<body>
  <div class="container">
    <h2 class="page-header">jsonp</h2>
    <div id="result"></div>
  </div>

  <script>
    //处理数据
    function handle (data) {
      //获取 result 元素
      const result = document.getElementById('result');
      result.innerHTML = data.name;
    }
  </script>
</body>

<!-- <script src="./js/app.js"></script> -->
<script src="http://127.0.0.1:8000/jsonp-server"></script>


<!-- 
<body>
  <div class="container">
    <h2 class="page-header">同源策略</h2>
    <div id="result"></div>
  </div>

  <script>
    //处理数据
    function handle (data) {
      //获取 result 元素
      const result = document.getElementById('result');
      console.log(result);
      result.innerHTML = data.name;
    }
  </script>
  <script src="http://127.0.0.1:8000/jsonp-server"></script>
</body> -->

</html>
```
