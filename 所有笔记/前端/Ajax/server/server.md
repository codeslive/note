### 服务端代码

```javascript
//导入 express
const express = require('express');

//创建实例对象
const app = express();

//创建路由规则
app.get('/server', (req, res) => {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.send('HELLO AJAX GET');
});
//all可以接收任意类型的请求
app.all('/server', (req, res) => {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Headers', '*');
  res.send('HELLO AJAX POST');
});

app.all('/json-server', (req, res) => {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Headers', '*');

  const data = {
    name: 'xiaokang'
  };

  //对对象字符串进行转换
  let str = JSON.stringify(data);
  //设置响应体
  res.send(str);

  res.send('HELLO AJAX JSON');
});


app.get('/ie', (req, res) => {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Headers', '*');
  res.send('HELLO AJAX IE-2');
});

//监听端口
app.listen(8000, () => {
  console.log('服务已经启动, 8000端口正在运行在……');
});
```

