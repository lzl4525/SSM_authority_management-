# 基于MAVEN的SSM企业权限管理系统  

功能的介绍：

- 商品管理功能

- 订单管理

- 用户管理

- 角色管理

- 资源权限管理

- 权限关联控制

- AOP日志处理

  


# 1 用户、角色、资源权限CRUD及其关联

## 1.1 用户

​	实现用户的CRUD操作，实现用户密码加密操作

## 1.2 角色

   设置角色表，可与用户绑定。

## 1.3 资源权限

​	商品及订单的CRUD操作。

## 1.4 权限关联

### 1.4.1 用户绑定角色

​	实现用户和角色的绑定

### 1.4.2 角色和资源权限的绑定

​	不同角色具有的资源权限不同

# 2 Spring Security完成用户认证和授权

## 2.1 用户登陆退出操作

​	Spring Security控制用户的登陆退出操作

## 2.2 方法级权限控制

​    在服务器端通过Spring security提供的注解对方法来进行权限控制，pring Security在方法的权限控制上支持三种类型的注解。

- JSR-250注解

- @Secured注解

- 表达式的注解

​    这三种注解默认都是没有启用的，需要单独通过global-method-security元素的对应属性进行启用

# 3 系统级别的日志收集功能

## 3.1 建立sysLog实体类和数据库表

| 序号 | 字段名        | 字段描叙     |
| ---- | ------------- | ------------ |
| 1    | id            | 主键         |
| 2    | visitTime     | 访问时间     |
| 3    | username      | 操作者用户名 |
| 4    | ip            | 访问ip       |
| 5    | url           | 访问资源url  |
| 6    | executionTime | 执行市场     |
| 7    | methed        | 访问方法     |



### 3.1.2 创建切面处理类

使用前置通知和后置通知控制所有的controller方法，得到所有的字段信息，保存到数据库。

### 3.1.3 页面显示日志

完成日志展示功能
