### express路由

> 案例

*   html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>login</title>
</head>
<body>
  <form method="post" action="http://127.0.0.1:3000/login" >
      <button>登录</button>
  </form>
</body>
</html>
```

*   js

```javascript
//1. 导入express
const express = require('express');

//2. 创建应用对象
const app = express();

//3. 创建路由
app.get('/home',(req , res)=>{
  res.end('hello express');
});

app.get('/',(req , res)=>{
  res.end('home');
});

app.post('/login',(req , res)=>{
  res.end('login login');
})

//4. 监听端口，启动服务
app.listen(3000,()=>{
  console.log('服务已经启动，端口3000正在监听中……');
  
});

```

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304061930400.webp?x-oss-process=style/webp)

*   匹配所有路由

```javascript
//匹配所有方法
app.all('/test',(req, res)=>{
  res.end('test test');
});

```

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304062059672.webp?x-oss-process=style/webp)

*   404响应

```javascript
//404响应
app.all('*',(req ,res)=>{
  res.end('404 not Found');
});
```

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304062100212.webp?x-oss-process=style/webp)

### express获取请求参数

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304062109414.webp?x-oss-process=style/webp)

### 获取路由参数

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304062116789.webp?x-oss-process=style/webp)

### 设置响应

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304062128641.webp?x-oss-process=style/webp)

### 其他响应

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304062136081.webp?x-oss-process=style/webp)