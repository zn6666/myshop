# myshop
myshop是一套电商系统，包括前台商城系统、H5和微信小程序及后台管理系统，SpringCloud和SpringCloudAlibaba并采用前后端分离vue的企业级微服务实现，支持多租户。 前台商城系统基于Vue+Element实现包含首页门户、商品推荐、商品搜索、商品展示、购物车、订单流程、支付模块、会员中心、客户服务、帮助中心等模块。后台管理系统包含商品管理、订单管理、会员管理、促销管理、运营管理、内容管理、统计报表、财务管理、权限管理、设置等模块。

# 1项目介绍
技术交流群 [807571015]


Github地址：https://github.com/fafalong/myshop

前后端分离的企业级微服务架构

基于Spring Boot 2.1.X、Spring Cloud Finchley和Spring Cloud Alibaba(注册中心和配置中心)

深度定制Spring Security真正实现了基于RBAC、jwt和oauth2的无状态统一权限认证的解决方案

引入组件化的思想实现高内聚低耦合，项目代码简洁注释丰富上手容易

注重代码规范，严格控制包依赖，每个工程基本都是最小依赖

非常适合学习和企业中使用
# 2项目总体架构图


# 功能介绍
统一认证功能

支持oauth2的四种模式登录
支持用户名、密码加图形验证码登录
支持手机号加密码登录
支持openId登录
支持第三方系统单点登录
分布式系统基础支撑

服务注册发现、路由与负载均衡
服务降级与熔断
服务限流(url/方法级别)
统一配置中心
统一日志中心
统一分布式缓存操作类、cacheManager配置扩展
分布式锁
分布式任务调度器
支持CI/CD持续集成(包括前端和后端)
分布式高性能Id生成器
分布式事务
系统监控功能

服务调用链监控
应用拓扑图
慢服务检测
服务Metric监控
应用监控(应用健康、JVM、内存、线程)
错误日志查询
慢查询SQL监控
应用吞吐量监控(qps、rt)
服务降级、熔断监控
服务限流监控
分库分表、读写分离
业务基础功能支撑

高性能方法级幂等性支持
RBAC权限管理，实现细粒度控制(方法、url级别)
快速实现导入、导出功能
数据库访问层自动实现crud操作
代码生成器
基于Hutool的各种便利开发工具包
网关聚合所有服务的Swagger接口文档
统一跨域处理
统一异常处理

# 模块说明
myshop -- 父项目，公共依赖
│  ├─mall-business -- 业务模块一级工程
│  │  ├─user-center -- 用户中心[7000]
│  │  ├─file-center -- 文件中心[5000]
│  │  ├─member-center -- 会员中心[7001]
│  │  ├─goods-center -- 商品中心[7002]
│  │  ├─order-center -- 订单中心[7003]
│  │  ├─marking-center -- 营销中心[7004]
│  │─mall-commons -- 通用工具一级工程
│  │  ├─mall-auth-client-spring-boot-starter -- 封装spring security client端的通用操作逻辑
│  │  ├─mall-common-spring-boot-starter -- 封装通用操作逻辑
│  │  ├─mall-db-spring-boot-starter -- 封装数据库通用操作逻辑
│  │  ├─mall-log-spring-boot-starter -- 封装log通用操作逻辑
│  │  ├─mall-redis-spring-boot-starter -- 封装Redis通用操作逻辑
│  │  ├─mall-ribbon-spring-boot-starter -- 封装Ribbon和Feign的通用操作逻辑
│  │  ├─mall-sentinel-spring-boot-starter -- 封装Sentinel的通用操作逻辑
│  │  ├─mall-swagger2-spring-boot-starter -- 封装Swagger通用操作逻辑
│  ├─mall-config -- 配置中心
│  ├─mall-doc -- 项目文档
│  ├─mall-gateway -- api网关一级工程
│  │  ├─zuul-gateway -- netflix-zuul[8080]
│  ├─mall-job -- 分布式任务调度一级工程
│  │  ├─job-admin -- 任务管理器[8081]
│  │  ├─job-core -- 任务调度核心代码
│  │  ├─job-executor-samples -- 任务执行者executor样例[8082]
│  ├─mall-monitor -- 监控一级工程
│  │  ├─sc-admin -- 应用监控[6500]
│  │  ├─log-center -- 日志中心[6200]
│  ├─mall-uaa -- spring-security认证中心[8000]
│  ├─mall-register -- 注册中心Nacos[8848]
│  ├─mall-web -- 前端一级工程
│  │  ├─back-web -- 后台前端[8066]
│  ├─mall-transaction -- 事务一级工程
│  │  ├─txlcn-tm -- tx-lcn事务管理器[7970]
│  ├─mall-demo -- demo一级工程
│  │  ├─txlcn-demo -- txlcn的demo
│  │  ├─sharding-jdbc-demo -- sharding-jdbc的demo
