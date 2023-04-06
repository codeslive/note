### expreess启动

![](https://static-youdao-note.oss-cn-shenzhen.aliyuncs.com/images/202304061901046.webp?x-oss-process=style/webp)

### 代码

```javascript
//1. 导入express
const express = require('express');

//2. 创建应用对象
const app = express();

//3. 创建路由
app.get('/home',(req , res)=>{
  res.end('hello express');
});

//4. 监听端口，启动服务
app.listen(3000,()=>{
  console.log('服务已经启动，端口3000正在监听中……');
  
});

```