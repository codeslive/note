### 请求体数据获取

> 实现功能

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304071145456.webp?x-oss-process=style/webp)

> 实现代码

- html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>登录页面</title>
</head>
<body>
  <h2>用户登录</h2>
  <hr/>
  <form method="post" action="/login">
      用户名：<input type="text" name="username"><br/>
      密码：<input type="password" name="password"><br/>
      <button>登录</button>
  </form>
</body>
</html>
```

- js

```javascript
//1. 导入express
const bodyParser = require('body-parser');
const express = require('express');

//2. 创建应用对象
const app = express();

//解析 JSON 格式的请求体中间件
const jsonParser = bodyParser.json();

//解析 querystring 格式请求体的中间件
const urlencodeParser = bodyParser.urlencoded({extended:false});

//创建路由规则
app.get('/login',(req, res)=>{
  res.sendFile(__dirname + '/06_form.html');
});

app.post('/login', urlencodeParser , (req, res)=>{
  res.send('获取用户数据');
});

//监听端口
app.listen(3000,()=>{
  console.log('服务已经启动，端口3000正在监听中……');
  
});
```
> 演示效果

- 登陆页面

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304071208885.webp?x-oss-process=style/webp)

- 跳转页面

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304071209083.webp?x-oss-process=style/webp)

- 请求数据

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304071210509.webp?x-oss-process=style/webp)