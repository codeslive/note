### 防盗链实践

> 实现功能

- 非127.0.0.1的图片资源无法显示
- 127.0.0.1的图片资源可以显示

> 实现代码

- html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>静态中间件</title>
</head>
<body>
  <h1>我是静态中间件</h1>
  <img src="images/code.png" alt="">
</body>
</html>
```

- js

```javascript
//1. 导入express
const express = require('express');

//2. 创建应用对象
const app = express();

//声明中间件
app.use((req, res, next)=>{
  //检测请求头中的 referer 是否为 127.0.0.1
  //获取 referer
  let referer = req.get('referer');
  if(referer){
    //实例化
    let url = new URL(referer);
    //获取hostname
    let hostname = url.hostname;
    //判断
    if(hostname !== '127.0.0.1'){
      //响应404
      res.status(404).send('<h1>404 Not Found</h1>');
    }
  }
  next();
  
})


//静态资源中间件设置
app.use(express.static(__dirname + '/public'))


//4. 监听端口，启动服务
app.listen(3000,()=>{
  console.log('服务已经启动，端口3000正在监听中……');
  
});

```
> 演示效果

- 127.0.0.1(图片正常响应)

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304071236001.webp?x-oss-process=style/webp)

- localhost(图片无法响应)

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304071237410.webp?x-oss-process=style/webp)