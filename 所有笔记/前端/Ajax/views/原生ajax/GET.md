### ajax get请求案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ajax GET 请求</title>
</head>
<style>
    #result{
      width: 200px;
      height: 100px;
      border: solid 1px #90b;
    }
</style>
<body>
  <button>点击发送请求</button>
  <div id="result"></div>
</body>
</html>

<script>
  //获取button元素
  const btn = document.getElementsByTagName('button')[0];
  const result = document.getElementById('result');
  //绑定事件
  btn.onclick = function(){
    //创建对象
    const xhr = new XMLHttpRequest();
    //初始化 设置请求方法和 url
    xhr.open('GET', 'http://127.0.0.1:8000/server?a=100&b=200&c=300');
    //发送
    xhr.send();
    //事件绑定 处理服务端返回的结果
    xhr.onreadystatechange = function(){
      //判断 (服务端返回了所有的结果)
      if(xhr.readyState === 4){
        if(xhr.status >= 200 && xhr.status < 300){
          //处理结果 行 头 空行 体
          // 相应行
          console.log(xhr.status); //状态码
          console.log(xhr.statusText); //状态码字符串
          console.log(xhr.getAllResponseHeaders()); //所有响应头
          console.log(xhr.response); //响应体

          result.innerHTML = xhr.response;
        }
      }
    }
  }
</script>
```

