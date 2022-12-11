# HTTP

## 1.HTTP是什么

超文本传输协议

HTML：超文本标记语言

HTML、JS、CSS、图片、字体、音频、视频等文件，都是通过HTTP传输的

每一次前后端通信，前端需要主动向后端发出请求，后端收到前端的请求后，可以给出响应

HTTP是一个请求-响应协议

## 2.HTTP请求响应的过程

## 3.HTTP报文

### 1.报文是什么

浏览器向服务器发送请求时，请求本身就是信息，叫请求报文

服务器向浏览器发送响应时传输的信息，叫响应报文

### 2.HTTP报文格式

![image-20220801224132711](C:\Users\L1145\AppData\Roaming\Typora\typora-user-images\image-20220801224132711.png)

请求

请求头：起始行+首部

请求体

GET请求，没用请求体，数据通过请求头携带

POST请求，有请求体，数据通过请求体携带



响应

响应头：起始行+首部

响应体



## 4.HTTP方法

### 1.常用的HTTP方法

浏览器发送请求时采用的方法，和响应无关

GET、POST、PUT、DELETE

用来定义对于资源采取什么样的操作，有各自的语义

### 2.HTTP方法的语义

GET获取数据

获取资源（文件）



POST创建数据

注册



PUT更新数据

修改个人信息、修改密码



DELETE删除数据

删除一条评论



这些方法虽然有各自的语义，但是并不是强制性的

### 3.RESTful接口设计

一种接口设计风格，充分利用HTTP方法的语义

例如：

通过用户ID获取个人信息，使用GET方法

https://www.bilibili.com/api/http/getUser?id=1

GET

https://www.bilibili.com/api/http/user?id=1



注册新用户，使用POST方法

https://www.bilibili.com/api/http/addUser

POST

https://www.bilibili.com/api/http/user



修改一个用户，使用POST

https://www.bilibili.com/api/http/modifyUser

PUT

https://www.bilibili.com/api/http/user



删除一个用户，使用POST方法

https://www.bilibili.com/api/http/deleteUser

DELETE

https://www.bilibili.com/api/http/user



## 5.GET和POST对比

### 1.语义

GET：获取数据

POST：创建数据

### 2.发送数据

GET通过地址在请求头中携带数据

能携带的数据量和地址的长度有关系，一般最多几k



POST既可以通过地址在请求头中携带数据，也可以通过请求体携带数据

能携带的数据量理论上是无限的



携带少量数据，可以使用GET请求，大量的数据使用POST请求



### 3.缓存

GET可以被缓存，POST不会被缓存



### 4.安全性

?username=alex

GET和POST都不安全



发送密码或者其他敏感信息时不要使用GET，主要避免直接被他人窥屏或通过历史记录找到你的密码



## 6.HTTP状态码

### 1.HTTP状态码是什么

定义服务器对请求的处理结果，是服务器返回的

### 2.HTTP状态码的语义

100-199 消息：代表请求已被接受，需要继续处理

websocket



200-299成功

200



300-399重定向

301 Moved Permanly永久性缓存

302 Move Temporari临时性跳转

304 Not Modified 没有修改



400-499请求错误

404 Not Found



500-599服务器错误

500 Internet Server Error
