package com.slociv.servlet;

import javax.servlet.*;
import java.io.IOException;

public class HelloServlet implements Servlet {
    /**
     * 当创建实例的时候，会调用init一次
     * @param servletConfig
     * @throws ServletException
     */
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {

    }

    /**
     * 返回ServletConfig 的配置
     * @return
     */
    @Override
    public ServletConfig getServletConfig() {
        return null;
    }

    /**
     * service方法会接受到2个对象，处理浏览器的请求
     * 当浏览器每次请求servlet时就会调用一次service
     * 当tomcat 调用该方法时，会把http请求数据封装成servletRequest对象
     * 可以通过servletRequest得到用户提交的数据
     * servletResponse 对象可以用于返回数据给tomcat并返回给浏览器
     * @param servletRequest
     * @param servletResponse
     * @throws ServletException
     * @throws IOException
     */
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {

    }

    /**
     * 返回servlet信息
     * @return
     */
    @Override
    public String getServletInfo() {
        return "";
    }

    /**
     * servlet销毁时被调用
     */
    @Override
    public void destroy() {

    }
}