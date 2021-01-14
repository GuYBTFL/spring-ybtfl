# spring-ybtfl
# 手写spring 

## 目的
加深对Spring的理解,学习Spring框架设计,提高自己的代码质量和风格,锻炼自己的思维能力
还有就是为了装X ~

## 思路
1) 配置阶段
   配置web.xml:
      · <sevlet>
      · 配置启动项 : XDispatcherServlet
      · 设定 init-param : contextConfigLocation = applicationContext.properties
      · 设定 url-pattern : /*
      · 配置 Annotation : @XController @XService @XAutowired @XRequestMapping

2) 初始化阶段
   IOC:
      · 调用init()方法: 加载配置文件
      · IOC 容器初始化: Map<String, Object>
      · 扫描相关的类 : scan-package = "com.spring.ybtfl"
      · 创建实例化并保存到容器 : 通过反射机制将类实例化到 IOC 容器中
   
   DI :
      · 进行 DI 操作 : 扫描IOC 容器中的实例,给没有赋值的属性自动赋值
      
   MVC:
      · 初始化 HandlerMapping : 将一个URL 和一个 Method 进行一对一的关联映射
      Map<String, Object>
      
3) 运行阶段
    · 调用doGet() / doPost() 方法 : Web容器调用 doGet() / doPost() 方法，获得request / response 对象
    · 匹配HandleMapping : 从request对象中获取用户输入的url, 找到其对应的Method
    · 反射调用 method.invoker() : 利用反射调用方法并返回
    · response.getWrite().write() : 将结果输出到浏览器
    
    
## 实现
熟读Spring  W3Cschool教程,梳理Spring相关定义，了解每个定义个的作用

