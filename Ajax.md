## Ajax


### Ajax Asynchronous Javascript And XML 异步JavaScript和XML

#### XMLHttpRequest对象
Ajax的核心是XMLHttpRequest对象（XHR）。XHR为向服务器发送请求和解析服务器响应提供了接口。能够以异步方式从服务器获取数据
XHR的主要方法有：

```javascript
1. void open(Stirng methos, String url, Boolean async)
  用于创建请求
  参数： 
      method: 请求方式，如post、get、delete...
      url:    请求的网络地址
      async:  是否异步
      
2. void send(String body)
  用于 发送请求
  参数：
      body：要发送的数据
      
3. void setRequestHeader(String header, String value)
  用于设置请求头
  参数：
      header： 请求的key
      value:   请求头的value
      
4. String getAllResponseHeaders()
  获取所有响应头
  返回执值：
     响应头数据

5. String getResponseHeader(String header)
   获取响应头中指定header的值
   
6. void abort()
  终止请求
```
#### XHR的主要属性有：

1. Number readyState 状态值（整数），可以确定请求响应过程当前活动阶段
 + 0： 未初始化 。未调用open()方法
 + 1： 启动。已经调用opent()方法，未调用send()方法
 + 2： 发送。已经调用send()方法，未收到响应
 + 3： 接收。已经接收到部分数据
 + 4： 完成。已经接收到全部数据，可以在客户端使用
2. Function onreadystatechange 当readyState的值改变时自动触发执行其对应的函数（回调函数）
3. String responseText作为响应主体被返回的文本 （字符串类型）
4. XmlDocument responseXML服务器端返回的数据 （XML对象）
5. Number status 状态码（整数），如 200, 404
6. String statusText状态文本字符串

### GET请求 

```javascript
 function createXHR(){
  var xhr = null;
  if(XMLHttpRequest){
   xhr = new XMLHttpRequest();
  }else{
   xhr = new ActiveXObject("Microsoft.XMLHTTP");
  }
  return xhr;
 }
 function Ajax(url){
  var xhr = createXHR();
  // 定义回调函数
  xhr.onreadystatechange = function() {
   if(xhr.readyState === 4 && xhr.status === 200){
    var data = xhr.responstText;
    console.log(data);
   }
  }
  xhr.open("get", url , true);
  xhr.send();
 }
 
```
