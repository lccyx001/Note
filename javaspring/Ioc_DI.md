# Ioc 和 DI

控制反转是什么，DI又是什么？

BeanFactory 提供Ioc（控制反转）实现接口 ，依赖注入通过 getter, setter 和 构造函数两种方式实现

ApplicationContext 在实现 BeanFactory功能基础上，进一步扩展了其他功能，包括资源加载，发布事件，支持国际化

