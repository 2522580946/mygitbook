# Servlet

Servlet是一种Java技术，用于开发基于Web的应用程序。Servlet运行在Web服务器上，可以接收客户端请求并生成响应。下面介绍一些Servlet的基本概念和使用方法。

## Servlet的核心概念

- Servlet容器：Servlet容器是运行Servlet的环境，也称为Web容器。常见的Servlet容器包括Tomcat、Jetty、JBoss等。
- Servlet生命周期：Servlet的生命周期由三个方法组成：init()、service()和destroy()。init()方法在Servlet被初始化时调用，service()方法在每次接收到客户端请求时调用，destroy()方法在Servlet被销毁时调用。
- Servlet API：Servlet API是一组Java类和接口，用于开发Servlet。常用的Servlet API包括javax.servlet和javax.servlet.http。

## Servlet的使用方法

使用Servlet可以分为以下几个步骤：

- 编写Servlet类：Servlet类是一个Java类，用于接收客户端请求并生成响应。在Servlet类中可以使用Servlet API提供的各种方法，例如doGet()、doPost()、getServletContext()等。
- 配置web.xml：在web.xml文件中配置Servlet的映射关系。例如：

```
xmlCopy code<servlet>
    <servlet-name>HelloServlet</servlet-name>
    <servlet-class>com.example.HelloServlet</servlet-class>
</servlet>
<servlet-mapping>
    <servlet-name>HelloServlet</servlet-name>
    <url-pattern>/hello</url-pattern>
</servlet-mapping>
```

这个配置将名为HelloServlet的Servlet映射到URL /hello上。

- 部署Web应用程序：将Servlet类和web.xml文件打包成WAR文件，并部署到Web容器中。

以下是一个使用Servlet的例子：

HelloServlet.java：

```
javaCopy codepackage com.example;

import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;

public class HelloServlet extends HttpServlet {
    public void doGet(HttpServletRequest request,
                      HttpServletResponse response)
        throws ServletException, IOException {
        response.setContentType("text/html;charset=UTF-8");
        PrintWriter out = response.getWriter();
        out.println("<html>");
        out.println("<head><title>Hello Servlet</title></head>");
        out.println("<body>");
        out.println("<h1>Hello, World!</h1>");
        out.println("</body></html>");
    }
}
```

web.xml：

```
xmlCopy code<servlet>
    <servlet-name>HelloServlet</servlet-name>
    <servlet-class>com.example.HelloServlet</servlet-class>
</servlet>
<servlet-mapping>
    <servlet-name>HelloServlet</servlet-name>
    <url-pattern>/hello</url-pattern>
</servlet-mapping>
```

在这个例子中，HelloServlet继承了HttpServlet类，并重写了doGet()方法来生成HTML响应。在web.xml文件中，将HelloServlet映射到URL /hello上。当客户端访问/hello时，HelloServlet会接收到请求并生成响应。
