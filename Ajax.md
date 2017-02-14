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
