# spring5
# 1.IOC xml操作bean管理
    spring有两种bean，一种普通bean，一种工厂bean（factoryBean）
    1.1普通bean：在配置文件中定义bean类型就是返回类型
    1.2工厂bean：在配置文件中定义bean类型可以和返回类型不一样
        第一步 创建类，实现FactoryBean接口
        第二部 实现接口方法，在实现方法中定义返回类型
    1.3bean的生命周期
        （1）通过构造器创建bean实例
        （2）为bean设置属性值和对其他bean的引用
        （3）把bean实例传给bean后置处理器的方法，实现BeanPostprocessor接口
        （4）bean初始化方法
        （5）把bean实例传递给bean后置处理器的方法，实现BeanPostprocessor接口
        （6）bean可以使用
        （7）bean的销毁方法
        
# 2.IOC 注解操作bean管理
    @AutoWired  根据属性类型自动注入
    @Qualifier  根据属性名称自动注入
    @Resource   可以根据类型也可以根据名称自动注入
    @Value      注入普通类型属性
# 3.完全注解开发
    3.1创建配置类，替代xml配置文件
        @Configuration  //作为配置类，替代xml配置文件
        @ComponentScan(basePackages = "com")
# 4.aop
    4.1jdk动态代理
        （1）创建接口
        （2）创建接口实现类
        （3）proxy代理
    4.2aop术语
        （1）连接点：类里面哪些方法可以被增强，这些方法称为连接点
        （2）切入点：实际被增强的方法称为切入点
        （3）通知（增强）：实际增强的逻辑部分称为通知
            通知类型
                *前置通知
                *后置通知
                *环绕通知
                *异常通知
                *最终通知
        （4）切面：把通知应用到切入点的过程
    4.3切入点表达式
        语法结构：
            execution([权限修饰符][返回类型][类全路径][方法名称][(参数列表)])
            execution(* com.aop.UserDao.add(..))
            execution(* com.aop.UserDao.*.*(..))
