# 项目结构说明

## 总体架构

本电商平台采用微服务架构设计，将整个系统拆分为多个独立的服务模块，每个模块负责特定的业务功能。

## 目录结构

```
ecommerce-platform/
├── backend/                    # 后端服务目录
│   ├── admin/                  # 后台管理服务
│   │   ├── src/main/java/      # Java源代码
│   │   ├── src/main/resources/ # 配置文件
│   │   ├── pom.xml            # Maven配置
│   │   └── Dockerfile         # 容器化配置
│   ├── payment/                # 支付服务
│   │   ├── src/main/java/
│   │   ├── src/main/resources/
│   │   ├── pom.xml
│   │   └── Dockerfile
│   ├── fulfillment/            # 履约服务
│   │   ├── src/main/java/
│   │   ├── src/main/resources/
│   │   ├── pom.xml
│   │   └── Dockerfile
│   └── order/                  # 订单服务
│       ├── src/main/java/
│       ├── src/main/resources/
│       ├── pom.xml
│       └── Dockerfile
├── frontend/                   # 前端应用目录
│   ├── admin/                  # 后台管理界面
│   │   ├── public/            # 静态资源
│   │   ├── src/               # 源代码
│   │   ├── package.json       # 依赖配置
│   │   └── Dockerfile         # 容器化配置
│   ├── customer/               # 客户端界面
│   │   ├── public/
│   │   ├── src/
│   │   ├── package.json
│   │   └── Dockerfile
│   └── components/             # 公共组件库
│       ├── src/
│       └── package.json
├── docs/                       # 文档目录
│   ├── project-structure.md    # 项目结构说明
│   ├── api-reference.md        # API接口文档
│   ├── deployment-guide.md     # 部署指南
│   └── architecture-overview.md # 架构概览
└── docker-compose.yml          # 容器编排配置
```

## 后端服务详解

### 1. 后台管理服务 (admin)

负责：
- 用户认证和授权
- 商品信息管理
- 订单查看和处理
- 数据统计和报表
- 系统配置管理

技术栈：
- Spring Boot
- Spring Security
- JWT
- MyBatis Plus
- MySQL
- Redis

### 2. 支付服务 (payment)

负责：
- 处理支付请求
- 集成第三方支付渠道
- 退款处理
- 支付状态同步
- 支付安全验证

技术栈：
- Spring Boot
- Spring Cloud
- 支付宝/微信支付SDK
- RabbitMQ
- MySQL

### 3. 履约服务 (fulfillment)

负责：
- 库存管理
- 订单履约流程
- 物流信息跟踪
- 发货处理
- 售后服务支持

技术栈：
- Spring Boot
- Spring Data JPA
- Redis
- RabbitMQ
- Elasticsearch

### 4. 订单服务 (order)

负责：
- 订单创建和管理
- 订单状态流转
- 订单查询和统计
- 优惠券和促销活动
- 订单事件通知

技术栈：
- Spring Boot
- Spring Cloud Stream
- MySQL
- Redis

## 前端应用详解

### 1. 后台管理界面 (admin)

面向对象：运营管理人员、客服人员、管理员

功能：
- 商品管理界面
- 订单管理界面
- 用户管理界面
- 数据统计界面
- 系统设置界面

技术栈：
- React
- TypeScript
- Ant Design
- Redux Toolkit
- Axios

### 2. 客户端界面 (customer)

面向对象：终端用户

功能：
- 商品浏览和搜索
- 购物车管理
- 订单提交
- 个人中心
- 支付页面

技术栈：
- React
- TypeScript
- Styled Components
- React Router
- Axios

### 3. 公共组件库 (components)

包含：
- UI组件库
- 工具函数
- 通用样式
- 公共Hook

## 部署架构

使用Docker Compose进行本地部署，Kubernetes进行生产环境部署。