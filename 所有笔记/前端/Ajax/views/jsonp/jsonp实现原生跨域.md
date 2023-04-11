```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>jsonp实现原生跨域</title>
  <!-- 最新版本的 Bootstrap 核心 CSS 文件 -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    integrity="sha384-HSMxcRTRxnN+Bdg0JdbxYKrThecOKuH5zCYotlSAcp1+c8xmyTe9GYg1l9a69psu" crossorigin="anonymous">
  <!-- <script src="https://cdn.bootcdn.net/ajax/libs/axios/1.3.5/axios.js" crossorigin="anonymous"></script> -->

</head>

<body>
  <div class="container">
    <h2 class="page-header">jsonp实现原生跨域</h2>
    用户名：<input type="text" id="username">
    <p></p>
  </div>

  <script>
    //获取input元素
    const input = document.querySelector('input');
    const p = document.querySelector('p');
  
    //处理数据
    function handle (data) {
      input.style.border = "solid 1px #f00"  
      //修改 p 标签的提示文本
      p.innerHTML = data.msg;
    }

    input.onblur = function(){
      //获取用户的输入值
      let username = this.value;
      //向服务端发送请求 检测用户是否存在
      //创建script
      const script = document.createElement('script');
      //设置标签src的属性
      script.src = 'http://127.0.0.1:8000/check-username';
      //将script插入到文档中
      document.body.appendChild(script);
    }

  </script>
</body>





</html>
```
