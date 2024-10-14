idea快捷键：查看类的子接口和实现类ctrl+alt+鼠标左键


package com.slociv.servlet;

import javax.servlet.*;
import javax.servlet.http.HttpServletRequest;
import java.io.IOException;

public class HelloServlet implements Servlet {
    private int count = 0;
    /**
     * 当创建实例的时候，会调用init一次
     * @param servletConfig
     * @throws ServletException
     */
    @Override
    public void init(ServletConfig servletConfig) throws ServletException {
        System.out.println("init()被调用");
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
     *
     * @param servletRequest
     * @param servletResponse
     * @throws ServletException
     * @throws IOException
     */
    @Override
    public void service(ServletRequest servletRequest, ServletResponse servletResponse) throws ServletException, IOException {
        //因为代码中servletRequest没有getmethod方法所以要转换成子接口的httpservletrequest
        HttpServletRequest request = (HttpServletRequest) servletRequest;
        String method = request.getMethod();
        if("GET".equals(method)) {
            doGet();
        }else if("POST".equals(method)) {
            doPost();
        }
    }

    private void doPost() {
        System.out.println("dopost被调用");
    }

    private void doGet() {
        System.out.println("doget被调用");
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
        System.out.printf("destory被调用");
    }
}
