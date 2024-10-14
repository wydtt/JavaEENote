1.每收到一个http请求server会创建一个线程处理

//Tomcat 每收到一个http请求会创建一个线程
Thread.currentThread().getId();

为什么他要封装一个servletrequest对象给你
因为他也可以把所有的参数给你，但那就是tomcat存在的意义，简化代码，要不然太多写不死页要累死