package com.slociv.servlet.annotation;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import java.io.IOException;

/**
 * 注解方式配置servlet
 * @WebServlet(urlPatterns = {"/ok1","/ok2"}) 是一个注解java基础注解
 */
@WebServlet(urlPatterns = {"/ok1","/ok2"})
public class OkServlet extends HttpServlet {

    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("注解诶方式okservelt dopost");
    }

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
        System.out.println("注解诶方式okservelt doget");
    }
}
