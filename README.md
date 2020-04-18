# Spring Boot For Crm-back

## 文档

- 保密文档，交付给委托人

## 概述

利用 Spring Boot 搭建，便于以后项目进行扩展，进行分布式部署。

## 开发工具

工具 | 地址 
----|----
Intellij IDEA | https://www.jetbrains.com/idea/download 
FinalShell | http://www.hostbuf.com/ 
Postman | https://www.getpostman.com/downloads/ 
Navicat for mysql | https://www.navicat.com.cn/products/navicat-for-mysql/
亿图图示 | https://www.edrawsoft.cn/edrawmax/ 

## 开发环境

- 操作系统：Windows 10 Enterprise
- 开发工具：Intellij IDEA
- 数据库：MySQL 8.0.13
- Java SDK：Oracle JDK 1.8.152

## 部署环境

- 操作系统：Linux centos7
- 虚拟化技术：VMware

## 项目管理工具

- 项目构建：Maven
- 代码管理：Git + GitLab

## 后台主要技术栈

- 核心框架：Spring Boot 
- ORM 框架：tk.mybatis 简化 MyBatis 开发
- Apache POI：Excel表格解析,文件上传
- 数据库连接池：Alibaba Druid
- 反向代理负载均衡：Nginx
- //短信平台待确认

## 前后分离

- 前端框架：JQuery+BootStrap
- 前端模板：thymeleaf

## 持续集成

- 持续集成：GitLab

## 拓扑结构

- pc ===> nginx ===> service

## 后台功能清单

### 后台登录、注册

功能 | 说明 
----|----|
添加账号 | 超级管理员或京纪人进行后台用户的添加，授权 | 
账号登录 | 用户输入密码，后台进行加密对比，授权功能。超时自动下线 | 

### 权限管理

角色 | 菜单 | 按钮
----|----|----| 
超级管理员 | 所有菜单权限 | 所有按钮权限 | 
代理商 | 订单管理权限 | 订单提交，筛选（自己相关的订单），查看 ，上传，下载| 
京纪人 | 订单管理权限 | 订单审核，筛选（所有代理商），查看，创建，修改，上传，下载| 
总代   | 订单管理权限 | 订单审核，筛选（所有代理商），查看，下载| 

功能 | 说明 
----|----|
权限管理 | 添加权限、删除权限、修改权限、以树形结构返回权限 | 
角色管理 | 添加角色、删除角色、更新角色、角色列表、获取角色权限、修改角色权限 | 
成员管理 | CRUD、为成员分配角色、获取成员角色、权限分配、获取权限列表 | 

## 公共功能清单

功能 | 说明 
----|----
用户密码修改 | 通过旧密码，更换新密码 | 
基本信息修改 | 修改头像相关的信息     | 
FAQ          | 常用文档，问题和答案   | 

## 服务规划

### Cloud

| 服务名称    | 服务端口         | 服务说明                               |
| --------------- | -------------------- | ------------------------------ |
| MySQL           | ip addr :3306  | MySQL 8.x，1G                        |
| GitLab          | ip addr1 :8080  | 代码托管/持续集成，2G               |

### Services

| 服务名称           | 服务端口 | 服务说明   |
| ------------------ | -------- | ---------- |
| crm-back           | 随机     | 管理后台   |
