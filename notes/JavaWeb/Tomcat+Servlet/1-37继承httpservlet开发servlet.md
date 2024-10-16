web.xml配置

```xml
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee http://xmlns.jcp.org/xml/ns/javaee/web-app_4_0.xsd"
         version="4.0">
<!--    web.xml主要来配置该web使用到的servlet-->
    <servlet>
        <servlet-name>HelloServlet</servlet-name>
        <servlet-class>com.slociv.servlet.HelloServlet</servlet-class>
<!--        <load-on-startup>1</load-on-startup>-->
    </servlet>
    <servlet-mapping>
        <servlet-name>HelloServlet</servlet-name>
        <url-pattern>/helloServlet</url-pattern>
    </servlet-mapping>
    <servlet>
        <servlet-name>HiServlet</servlet-name>
        <servlet-class>com.slociv.servlet.HiServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>HiServlet</servlet-name>
        <url-pattern>/hiServlet</url-pattern>
    </servlet-mapping>
</web-app>
```
HiServlet.class

```java
package com.slociv.servlet;

import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

public class HiServlet extends HttpServlet {
    //重写httpservlet的doget和dopost方法

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("hiservlet doget()...");
    }

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("hiservlet dopost()...");
    }
}

```

