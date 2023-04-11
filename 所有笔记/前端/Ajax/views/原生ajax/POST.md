### ajax post请求案例

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ajax POST 请求</title>
</head>
<style>
  #result {
    width: 200px;
    height: 100px;
    border: solid 1px #90b;
  }
</style>

<body>
  <div id="result"></div>
</body>

</html>

<script>
  //获取元素对象
  const result = document.getElementById('result');
  //绑定事件
  result.addEventListener("mouseover", function () {
    //创建对象
    const xhr = new XMLHttpRequest();
    //初始化 设置类型 URL
    xhr.open('POST', 'http://127.0.0.1:8000/server');
    //设置请求头信息
    xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
    xhr.setRequestHeader('name', 'xiaokang');
    console.log('1');
    //发送
    xhr.send('a=100&b=200&c=300');
    //事件绑定
    xhr.onreadystatechange = function () {
      //判断
      if (xhr.readyState === 4) {
        if (xhr.status >= 200 && xhr.status < 300) {
          //处理服务端返回的结果
          result.innerHTML = xhr.response;
        }
      }
    }
  });
</script>
```