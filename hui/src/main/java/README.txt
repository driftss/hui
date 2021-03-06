
@Copyright by SONG

h-ui:
专注于前端页面的框架, 后台管理系统的模板

1.LoginServlet
2.index.html
  导入所需的 js css
  jquery.js
  h-ui - css | js
  h-ui.admin - css | js
3.jquery -> LoginServlet 无刷新登录
4.main.html



Restful风格的API是一种软件架构风格，设计风格而不是标准，只是提供了一组设计原则和约束条件。它主要用于客户端和服务器交互类的软件。基于这个风格设计的软件可以更简洁，更有层次，更易于实现缓存等机制。

在Restful风格中，用户请求的url使用同一个url而用请求方式：get，post，delete，put...等方式对请求的处理方法进行区分，这样可以在前后台分离式的开发中使得前端开发人员不会对请求的资源地址产生混淆和大量的检查方法名的麻烦，形成一个统一的接口。

在Restful风格中，现有规定如下：

GET（SELECT）：从服务器查询，可以在服务器通过请求的参数区分查询的方式。
POST（CREATE）：在服务器新建一个资源，调用insert操作。
PUT（UPDATE）：在服务器更新资源，调用update操作。
PATCH（UPDATE）：在服务器更新资源（客户端提供改变的属性）。(目前jdk7未实现，tomcat7也不行)。
DELETE（DELETE）：从服务器删除资源，调用delete语句。
了解这个风格定义以后，我们举个例子：

如果当前url是 http://localhost:8080/User

那么用户只要请求这样同一个URL就可以实现不同的增删改查操作，例如

http://localhost:8080/User?_method=get&id=1001　　这样就可以通过get请求获取到数据库 user 表里面 id=1001 的用户信息

http://localhost:8080/User?_method=post&id=1001&name=zhangsan　　这样可以向数据库 user 表里面插入一条记录

http://localhost:8080/User?_method=put&id=1001&name=lisi　　这样可以将 user表里面 id=1001 的用户名改为lisi

http://localhost:8080/User?_method=delete&id=1001　　这样用于将数据库 user 表里面的id=1001 的信息删除

这样定义的规范我们就可以称之为restful风格的API接口，我们可以通过同一个url来实现各种操作。
