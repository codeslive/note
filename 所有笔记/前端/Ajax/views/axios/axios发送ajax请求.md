```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>axios发送ajax请求</title>
  <!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">
  <script src="https://cdn.bootcdn.net/ajax/libs/axios/1.3.5/axios.js" crossorigin="anonymous"></script>
</head>

<body>
  <div class="container">
    <h2 class="page-header">axios发送ajax请求</h2>
    <button class="btn btn-primary">GET</button>
    <button class="btn btn-danger">POST</button>
    <button class="btn btn-info">AJAX</button>
  </div>
</body>

</html>

<script>
  const btns = document.querySelectorAll('button');

  //配置 baseURL
  axios.defaults.baseURL = 'http://127.0.0.1:8000';

  //get
  btns[0].onclick = function () {
    //GET 请求
    axios.get('/axios-server', {
      //url 参数
      params: {
        id: 100,
        vip: 7
      },

      //请求头信息
      headers: {
        name: 'xiaokang',
        age: 20
      }
    }).then(value => {
      console.log(value);
    });
  };

  btns[1].onclick = function () {
    axios.post('/axios-server', {
      username: 'admin',
      password: 'admin'
    }, {
      params: {
        id: 200,
        vip: 9
      },

      //请求头参数
      headers: {
        height: 180,
        weight: 180,
      }

    })
  };


  btns[2].onclick = function () {
    axios({
      //请求方法
      method: 'POST',
      //url
      url: '/axios-server',
      //url参数
      params: {
        vip: 10,
        level: 30
      },
      //头信息
      headers: {
        a: 100,
        b: 200
      },
      data: {
        username: 'admin',
        password: 'admin'
      }

    }).then(res => {
      //响应状态码
      console.log(res.status);
      //响应状态字符串
      console.log(res.statusText);
      //响应头信息
      console.log(res.headers);
      //响应体
      console.log(res.data);

    });
  }

</script>
```
