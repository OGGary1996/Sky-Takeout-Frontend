# Sky Takeout Management System

<div align="center">

**A Modern Restaurant Takeout Management System Built with Vue + TypeScript + Element UI**

[![Vue](https://img.shields.io/badge/Vue-2.6.10-brightgreen.svg)](https://vuejs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3.6.2-blue.svg)](https://www.typescriptlang.org/)
[![Element UI](https://img.shields.io/badge/Element%20UI-2.12.0-409EFF.svg)](https://element.eleme.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

[English](#english) | [中文](#chinese)

</div>

---

<a name="english"></a>

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Core Features](#-core-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Quick Start](#-quick-start)
- [Configuration](#-configuration)
- [Feature Details](#-feature-details)
- [Development Guide](#-development-guide)
- [Version History](#-version-history)
- [Resources](#-resources)

---

## 📖 Project Overview

Sky Takeout Management System is a modern management platform designed for the restaurant industry. It aims to solve problems such as module fragmentation, information asymmetry, and high communication costs in traditional restaurant systems. The system adopts a front-end and back-end separation architecture. This project is the front-end part, providing complete store management, employee management, dish management, order management, and data statistics functions.

### Highlights

- 🎯 **Modern Tech Stack** - Built on Vue 2.6 + TypeScript 3.6, type-safe code
- 🎨 **Elegant UI Design** - Using Element UI component library, beautiful and user-friendly interface
- 📊 **Rich Data Visualization** - Integrated with ECharts 5.3, supports multiple chart displays
- 🔐 **Complete Permission Management** - Token-based authentication and route guards
- 🚀 **High Performance Optimization** - Request deduplication, route lazy loading, on-demand component import
- 📱 **Responsive Layout** - Adapts to different screen sizes, provides excellent user experience
- 🔊 **Real-time Order Alerts** - Supports voice notifications for timely order processing

---

## ✨ Core Features

### 🏪 Store Management
- **Dashboard** - Real-time data overview, business data statistics, order statistics, dish overview
- **Data Statistics** - Revenue statistics, user statistics, order statistics, TOP10 sales, data export

### 👥 Employee Management
- CRUD operations for employee information
- Enable/Disable employee accounts
- Employee permission management
- Search employees by name

### 📂 Category Management
- Dish category and combo category management
- Enable/Disable category status control
- Search categories by name and type
- Category sorting functionality

### 🍜 Dish Management
- CRUD operations for dish information
- Dish image upload
- Dish flavor configuration
- Filter by category and sales status
- Dish on sale/off sale management
- Batch on sale/off sale

### 🍱 Combo Management
- CRUD operations for combo information
- Combo image upload
- Combo associated dish configuration
- Filter by category and sales status
- Combo on sale/off sale management
- Batch on sale/off sale

### 📦 Order Management
- Order list display (All orders, Pending, To be delivered, In delivery, Completed, Cancelled)
- View order details
- Order status switching (Accept, Reject, Deliver, Complete, Cancel)
- Voice notification for new orders
- Filter by order number, phone number, date

### 📈 Data Statistics
- **Revenue Statistics** - Revenue trend chart within time period
- **User Statistics** - User growth trend analysis
- **Order Statistics** - Order volume and order status distribution
- **Sales Ranking** - TOP10 best-selling dishes/combos
- **Data Overview** - Comprehensive data dashboard
- **Data Export** - Supports Excel export

### 🔔 Notification Center
- System message notifications
- Order reminders
- Mark messages as read/unread

---

## 🛠 Tech Stack

### Core Framework
- **Vue 2.6.10** - Progressive JavaScript framework
- **TypeScript 3.6.2** - Superset of JavaScript, provides type safety
- **Vue Router 3.1.2** - Official router for Vue.js
- **Vuex 3.1.1** - State management pattern for Vue.js

### UI Framework & Components
- **Element UI 2.12.0** - Desktop UI component library based on Vue 2.0
- **ECharts 5.3.2** - Powerful data visualization library
- **vue-svgicon 3.2.6** - SVG icon component

### Utility Libraries
- **Axios 0.19.0** - Promise-based HTTP client
- **js-cookie 2.2.1** - Lightweight cookie handling library
- **moment 2.24.0** - Date and time processing library
- **md5 2.3.0** - MD5 encryption algorithm
- **nprogress 0.2.0** - Page loading progress bar

### Development Tools
- **Vue CLI 3.11.0** - Standard tooling for Vue.js development
- **Sass 1.22.10** - CSS preprocessor
- **ESLint 6.2.2** - JavaScript code linting tool
- **Jest 24.9.0** - JavaScript testing framework
- **Cypress** - E2E testing framework
- **Webpack 4.39.3** - Module bundler

### Other Features
- **PWA Support** - Supports offline access and add to home screen
- **Vuex Persistence** - vuex-persistedstate state persistence
- **Decorator Syntax** - vue-class-component & vue-property-decorator
- **CSS Normalize** - normalize.css style reset

---

## 📁 Project Structure

```
sky-takeout-frontend/
├── public/                          # Static resources directory
│   ├── favicon.ico                  # Website icon
│   ├── index.html                   # HTML template
│   ├── manifest.json                # PWA configuration file
│   └── img/                         # Static image resources
│
├── src/                             # Source code directory
│   ├── api/                         # API interface definitions
│   │   ├── index.ts                 # Main interface (data statistics, reports)
│   │   ├── employee.ts              # Employee-related interfaces
│   │   ├── category.ts              # Category-related interfaces
│   │   ├── dish.ts                  # Dish-related interfaces
│   │   ├── setMeal.ts               # Combo-related interfaces
│   │   ├── order.ts                 # Order-related interfaces
│   │   ├── charts.ts                # Chart data interfaces
│   │   ├── users.ts                 # User-related interfaces
│   │   └── inform.ts                # Notification-related interfaces
│   │
│   ├── assets/                      # Static resources (processed by webpack)
│   │   ├── icons/                   # Icon resources
│   │   ├── login/                   # Login page images
│   │   ├── 404-images/              # 404 page images
│   │   ├── *.mp3                    # Audio files (order alerts)
│   │   └── *.png                    # Common images
│   │
│   ├── components/                  # Global common components
│   │   ├── Breadcrumb/              # Breadcrumb navigation
│   │   ├── Charts/                  # Chart components (bar, line, mixed charts)
│   │   ├── Empty/                   # Empty state component
│   │   ├── Hamburger/               # Sidebar collapse button
│   │   ├── HeadLable/               # Page title component
│   │   ├── ImgUpload/               # Image upload component
│   │   └── InputAutoComplete/       # Autocomplete input
│   │
│   ├── icons/                       # SVG icons
│   │   ├── svg/                     # SVG source files
│   │   └── components/              # SVG components (auto-generated)
│   │
│   ├── layout/                      # Layout components
│   │   ├── index.vue                # Main layout container
│   │   ├── components/
│   │   │   ├── AppMain.vue          # Main content area
│   │   │   ├── Navbar/              # Top navigation bar
│   │   │   └── Sidebar/             # Sidebar
│   │   └── mixin/
│   │       └── resize.ts            # Responsive layout mixin
│   │
│   ├── store/                       # Vuex state management
│   │   ├── index.ts                 # Store entry
│   │   └── modules/
│   │       ├── app.ts               # Application global state
│   │       └── user.ts              # User state
│   │
│   ├── styles/                      # Global styles
│   │   ├── index.scss               # Style entry
│   │   ├── element-variables.scss   # Element UI theme customization
│   │   ├── newRJWMsystem.scss       # Reggie takeout system styles
│   │   ├── sidebar.scss             # Sidebar styles
│   │   ├── home.scss                # Home page styles
│   │   ├── _variables.scss          # SCSS variables
│   │   ├── _mixins.scss             # SCSS mixins
│   │   ├── _transition.scss         # Transition animations
│   │   ├── _svgicon.scss            # SVG icon styles
│   │   └── icon/                    # Font icons
│   │
│   ├── utils/                       # Utility functions
│   │   ├── request.ts               # Axios request wrapper
│   │   ├── requestOptimize.ts       # Request deduplication optimization
│   │   ├── cookies.ts               # Cookie operation wrapper
│   │   ├── validate.ts              # Form validation rules
│   │   ├── formValidate.ts          # Form validation methods
│   │   └── common.ts                # Common utility functions
│   │
│   ├── views/                       # Page views
│   │   ├── login/                   # Login page
│   │   ├── dashboard/               # Dashboard
│   │   ├── employee/                # Employee management
│   │   ├── category/                # Category management
│   │   ├── dish/                    # Dish management
│   │   ├── setmeal/                 # Combo management
│   │   ├── orderDetails/            # Order management
│   │   ├── statistics/              # Data statistics
│   │   ├── chart/                   # Chart pages
│   │   ├── inform/                  # Notification center
│   │   └── 404.vue                  # 404 page
│   │
│   ├── App.vue                      # Root component
│   ├── main.ts                      # Application entry file
│   ├── router.ts                    # Route configuration
│   ├── permission.ts                # Route permission control
│   ├── config.json                  # Application config (image server address, etc.)
│   ├── shims-vue.d.ts               # Vue type declarations
│   └── registerServiceWorker.ts     # PWA Service Worker
│
├── tests/                           # Test files
│   └── unit/                        # Unit tests
│       ├── components/              # Component tests
│       └── utils/                   # Utility function tests
│
├── .browserslistrc                  # Browser compatibility configuration
├── .editorconfig                    # Editor configuration
├── babel.config.js                  # Babel configuration
├── cypress.json                     # Cypress E2E test configuration
├── jest.config.js                   # Jest unit test configuration
├── postcss.config.js                # PostCSS configuration
├── tsconfig.json                    # TypeScript configuration
├── vue.config.js                    # Vue CLI configuration (proxy, build, etc.)
├── Dockerfile                       # Docker container configuration
├── package.json                     # Project dependencies
└── README.md                        # Project documentation
```

---

## 🚀 Quick Start

### Requirements

- **Node.js**: >= 10.x
- **npm**: >= 6.x or **yarn**: >= 1.x

### Install Dependencies

```bash
# Using npm
npm install

# Or using yarn (recommended)
yarn install
```

### Start Development Server

```bash
# Using npm
npm run serve

# Or using yarn
yarn serve
```

After successful startup, the browser will automatically open `http://localhost:8081`

### Build for Production

```bash
# Production build (remove delete functionality)
npm run build
# Or
yarn build

# UAT build (keep delete functionality)
npm run build:uat
# Or
yarn build:uat
```

After build completion, the generated static files are in the `dist/` directory.

### Code Linting

```bash
npm run lint
# Or
yarn lint
```

### Run Tests

```bash
# Unit tests
npm run test:unit

# E2E tests
npm run test:e2e
```

---

## ⚙️ Configuration

### 1. Configure Backend API Address

Create or modify `.env` file in the project root directory:

```env
# Development environment
VUE_APP_BASE_API = '/api'
VUE_APP_URL = 'http://localhost:8080'
```

### 2. Configure Image Server Address

Modify `src/config.json` file:

```json
{
  "baseUrl": "http://your-server-address:8200"
}
```

> **Note**: When deploying to production environment, you need to modify `baseUrl` to the actual server address.

### 3. Development Server Proxy Configuration

Proxy is already configured in `vue.config.js`, forwarding requests starting with `/api` to the backend server:

```javascript
proxy: {
  '/api': {
    target: process.env.VUE_APP_URL,  // Backend service address
    changeOrigin: true,
    pathRewrite: {
      '^/api': ''
    }
  }
}
```

---

## 📚 Feature Details

### 🔐 Login Authentication

- **Technical Implementation**:
  - Token-based authentication
  - Using js-cookie to store Token
  - MD5 encryption for user passwords
  - Route guards to control page access permissions

- **Login Process**:
  1. User enters username and password
  2. Frontend encrypts password using MD5
  3. Call login API to get Token
  4. Store Token in Cookie
  5. Redirect to dashboard page

### 📊 Dashboard

- **Today's Data Overview**:
  - Revenue statistics
  - Valid order count
  - Order completion rate
  - Average order value
  - New user count

- **Order Management Overview**:
  - Pending orders count
  - To be delivered count
  - In delivery count

- **Dish Overview**:
  - On sale dish count
  - Off sale dish count

- **Combo Overview**:
  - On sale combo count
  - Off sale combo count

### 👥 Employee Management

- **List Features**:
  - Paginated display of employee information
  - Search by employee name
  - Display account, name, phone, status, operation time

- **Operations**:
  - Add employee (name, username, phone, gender, ID number)
  - Edit employee information
  - Enable/Disable employee account
  - View employee details

### 📂 Category Management

- **List Features**:
  - Paginated display of category information
  - Search by category name
  - Filter by category type (Dish category/Combo category)
  - Display category name, type, sort order, status, operation time

- **Operations**:
  - Add category (name, type, sort order)
  - Edit category information
  - Enable/Disable category
  - Delete category (verify if associated with dishes/combos)

### 🍜 Dish Management

- **List Features**:
  - Paginated display of dish information
  - Search by dish name
  - Filter by dish category
  - Filter by sales status (On sale/Off sale)
  - Display dish image, name, category, price, sales status, operation time

- **Operations**:
  - Add dish (name, category, price, image, description, flavor)
  - Edit dish information
  - On sale/Off sale single dish
  - Batch on sale/off sale
  - Delete dish

- **Special Features**:
  - Image upload (supports image preview)
  - Flavor configuration (spiciness, temperature, dietary restrictions, etc.)
  - New dishes default to off sale status

### 🍱 Combo Management

- **List Features**:
  - Paginated display of combo information
  - Search by combo name
  - Filter by combo category
  - Filter by sales status (On sale/Off sale)
  - Display combo image, name, category, price, sales status, operation time

- **Operations**:
  - Add combo (name, category, price, image, description, associated dishes)
  - Edit combo information
  - On sale/Off sale single combo
  - Batch on sale/off sale
  - Delete combo

- **Special Features**:
  - Image upload (supports image preview)
  - Associated dish selector
  - Combo dish quantity configuration
  - New combos default to off sale status

### 📦 Order Management

- **Order Status Categories**:
  - All orders
  - Pending
  - To be delivered
  - In delivery
  - Completed
  - Cancelled

- **List Features**:
  - Switch by order status Tab
  - Search by order number
  - Search by phone number
  - Filter by order time
  - Display order number, status, user, phone, address, amount, order time

- **Operations**:
  - View order details (order info, recipient info, dish details)
  - Accept order (Pending → To be delivered)
  - Reject order (Pending → Cancelled, requires rejection reason)
  - Deliver (To be delivered → In delivery)
  - Complete (In delivery → Completed)
  - Cancel order (requires cancellation reason)

- **Special Features**:
  - New order voice notification
  - Real-time order status updates
  - Order quantity badge display

### 📈 Data Statistics

#### Revenue Statistics
- View revenue trends within selected time range
- Line chart showing daily/weekly/monthly revenue
- Supports today, last 7 days, last 30 days quick selection

#### User Statistics
- Total users and new user trends
- Line chart showing user growth
- Supports custom time range

#### Order Statistics
- Total orders and valid order count
- Order completion rate statistics
- Supports order status distribution pie chart

#### Sales Ranking TOP10
- Best-selling dishes/combos ranking
- Bar chart showing sales comparison
- Supports filtering by time range

#### Data Export
- Supports exporting operational data reports
- Excel format, includes complete statistical data

---

## 💻 Development Guide

### Code Standards

This project uses ESLint + TypeScript Standard code standards. Before submitting code, please ensure:

1. Code passes ESLint check: `npm run lint`
2. Follow TypeScript type specifications
3. Components use Class Component decorator syntax
4. API interfaces are defined uniformly in `src/api/` directory

### Component Development Standards

```typescript
import { Component, Vue } from 'vue-property-decorator'

@Component({
  name: 'ComponentName'
})
export default class ComponentName extends Vue {
  // Data properties
  private message: string = 'Hello'
  
  // Computed properties
  get computedValue() {
    return this.message
  }
  
  // Methods
  private handleClick() {
    // ...
  }
  
  // Lifecycle
  created() {
    // ...
  }
}
```

### API Interface Calls

```typescript
import { getEmployeeList } from '@/api/employee'

async fetchData() {
  try {
    const { data } = await getEmployeeList({ page: 1, pageSize: 10 })
    console.log(data)
  } catch (error) {
    console.error(error)
  }
}
```

### Vuex Usage

```typescript
import { Component, Vue } from 'vue-property-decorator'
import { UserModule } from '@/store/modules/user'

@Component
export default class Example extends Vue {
  get username() {
    return UserModule.username
  }
  
  logout() {
    UserModule.Logout()
  }
}
```

### Route Configuration

```typescript
{
  path: '/example',
  component: Layout,
  children: [
    {
      path: 'index',
      component: () => import('@/views/example/index.vue'),
      meta: {
        title: 'Example Page',
        icon: 'icon-example'
      }
    }
  ]
}
```

### Adding New Pages

1. Create page component in `src/views/`
2. Configure route in `src/router.ts`
3. Create corresponding interface file in `src/api/` (if needed)
4. Develop page functionality
5. Test if functionality works properly

### Image Upload

The project uses a custom `ImgUpload` component:

```vue
<template>
  <ImgUpload
    v-model="imageUrl"
    :action="uploadUrl"
  />
</template>

<script>
import ImgUpload from '@/components/ImgUpload/index.vue'

export default {
  components: { ImgUpload },
  data() {
    return {
      imageUrl: '',
      uploadUrl: '/common/upload'
    }
  }
}
</script>
```

### ECharts Usage

```typescript
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class ChartExample extends Vue {
  mounted() {
    this.initChart()
  }
  
  private initChart() {
    const chart = this.$echarts.init(this.$refs.chart as HTMLElement)
    chart.setOption({
      title: { text: 'Example Chart' },
      xAxis: { type: 'category', data: ['Mon', 'Tue', 'Wed'] },
      yAxis: { type: 'value' },
      series: [{ data: [120, 200, 150], type: 'line' }]
    })
  }
}
```

---

## 📝 Version History

### v1.3 (Latest)

**Developer**: Si Wenqiang

**Updates**:
- ✅ **Order Management Module**
  - Added order status switching Tab (All, Pending, To be delivered, In delivery, Completed, Cancelled)
  - Added order list fields and action buttons (Deliver, Accept, Reject, Cancel, Complete)
  - Added order details page (order info, recipient info, dish details)
  - Added order voice notification feature (real-time new order alerts)
  - Optimized order search and filter functionality

### v1.2

**Developer**: Si Wenqiang

**Updates**:
- ✅ **Employee Management Optimization**
  - Added modification time field
  - Changed status text from "Normal" to "Enabled"
  - Added query button
  
- ✅ **Category Management Optimization**
  - Added name and type filter in search conditions
  - Added status field
  - Added enable/disable functionality
  
- ✅ **Dish Management Optimization**
  - Added dish category filter in search conditions
  - Added sales status filter in search conditions
  - Added query button
  - New dishes default to disabled status
  
- ✅ **Combo Management Optimization**
  - Added combo category filter in search conditions
  - Added sales status filter in search conditions
  - Added query button
  - New combos default to disabled status
  
- ✅ **Other Optimizations**
  - Adjusted page styles and interactions according to design specs
  - Fixed bugs and issues in the above 4 modules

### v1.0

**Basic Features**:
- ✅ User login/logout
- ✅ Dashboard data overview
- ✅ Employee management basic features
- ✅ Category management basic features
- ✅ Dish management basic features
- ✅ Combo management basic features
- ✅ Data statistics basic features


---
---
---

<a name="chinese"></a>

# 苍穹外卖管理后台系统

<div align="center">

**基于 Vue + TypeScript + Element UI 构建的现代化餐饮外卖管理系统**

[![Vue](https://img.shields.io/badge/Vue-2.6.10-brightgreen.svg)](https://vuejs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-3.6.2-blue.svg)](https://www.typescriptlang.org/)
[![Element UI](https://img.shields.io/badge/Element%20UI-2.12.0-409EFF.svg)](https://element.eleme.io/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

</div>

---

## 📋 目录

- [项目简介](#-项目简介)
- [核心功能](#-核心功能)
- [技术栈](#-技术栈)
- [项目结构](#-项目结构)
- [快速开始](#-快速开始)
- [环境配置](#-环境配置)
- [功能模块详解](#-功能模块详解)
- [开发指南](#-开发指南)
- [版本迭代记录](#-版本迭代记录)
- [相关资源](#-相关资源)

---

## 📖 项目简介

苍穹外卖管理后台系统是一款面向餐饮行业的现代化管理平台，旨在解决传统餐饮系统中各模块相互割裂、信息不对称、沟通成本高等问题。系统采用前后端分离架构，本项目为前端部分，提供完整的门店管理、员工管理、菜品管理、订单管理和数据统计等功能。

### 项目特色

- 🎯 **现代化技术栈** - 基于 Vue 2.6 + TypeScript 3.6 构建，代码类型安全
- 🎨 **优雅的 UI 设计** - 采用 Element UI 组件库，界面美观易用
- 📊 **丰富的数据可视化** - 集成 ECharts 5.3，支持多种图表展示
- 🔐 **完善的权限管理** - 基于 Token 的身份认证和路由守卫
- 🚀 **高性能优化** - 请求去重、路由懒加载、组件按需引入
- 📱 **响应式布局** - 适配不同屏幕尺寸，提供良好的用户体验
- 🔊 **实时订单提醒** - 支持语音播报，及时处理新订单

---

## ✨ 核心功能

### 🏪 门店管理
- **工作台** - 实时数据概览、营业数据统计、订单统计、菜品总览
- **数据统计** - 营业额统计、用户统计、订单统计、销量TOP10、数据导出

### 👥 员工管理
- 员工信息的增删改查
- 员工账号的启用/禁用
- 员工权限管理
- 按姓名搜索员工

### 📂 分类管理
- 菜品分类和套餐分类管理
- 分类的启用/禁用状态控制
- 按名称和类型搜索分类
- 分类排序功能

### 🍜 菜品管理
- 菜品信息的增删改查
- 菜品图片上传
- 菜品口味配置
- 按分类和售卖状态筛选
- 菜品启售/停售管理
- 批量启售/停售

### 🍱 套餐管理
- 套餐信息的增删改查
- 套餐图片上传
- 套餐关联菜品配置
- 按分类和售卖状态筛选
- 套餐启售/停售管理
- 批量启售/停售

### 📦 订单管理
- 订单列表展示（全部订单、待接单、待派送、派送中、已完成、已取消）
- 订单详情查看
- 订单状态切换（接单、拒单、派送、完成、取消）
- 新订单语音播报提醒
- 按订单号、手机号、日期筛选

### 📈 数据统计
- **营业额统计** - 时间段内营业额趋势图
- **用户统计** - 用户增长趋势分析
- **订单统计** - 订单量和订单状态分布
- **销量排名** - TOP10 热销菜品/套餐
- **数据概览** - 综合数据看板
- **数据导出** - 支持 Excel 导出

### 🔔 通知中心
- 系统消息通知
- 订单提醒
- 消息标记已读/未读

---

## 🛠 技术栈

### 核心框架
- **Vue 2.6.10** - 渐进式 JavaScript 框架
- **TypeScript 3.6.2** - JavaScript 的超集，提供类型安全
- **Vue Router 3.1.2** - Vue.js 官方路由管理器
- **Vuex 3.1.1** - Vue.js 状态管理模式

### UI 框架与组件
- **Element UI 2.12.0** - 基于 Vue 2.0 的桌面端组件库
- **ECharts 5.3.2** - 强大的数据可视化库
- **vue-svgicon 3.2.6** - SVG 图标组件

### 工具库
- **Axios 0.19.0** - 基于 Promise 的 HTTP 客户端
- **js-cookie 2.2.1** - 轻量级 Cookie 处理库
- **moment 2.24.0** - 日期时间处理库
- **md5 2.3.0** - MD5 加密算法
- **nprogress 0.2.0** - 页面加载进度条

### 开发工具
- **Vue CLI 3.11.0** - Vue.js 开发标准工具
- **Sass 1.22.10** - CSS 预处理器
- **ESLint 6.2.2** - JavaScript 代码检查工具
- **Jest 24.9.0** - JavaScript 测试框架
- **Cypress** - E2E 测试框架
- **Webpack 4.39.3** - 模块打包器

### 其他特性
- **PWA 支持** - 支持离线访问和添加到主屏幕
- **Vuex 持久化** - vuex-persistedstate 状态持久化
- **装饰器语法** - vue-class-component & vue-property-decorator
- **CSS Normalize** - normalize.css 样式重置

---

## 📁 项目结构

```
sky-takeout-frontend/
├── public/                          # 静态资源目录
│   ├── favicon.ico                  # 网站图标
│   ├── index.html                   # HTML 模板
│   ├── manifest.json                # PWA 配置文件
│   └── img/                         # 静态图片资源
│
├── src/                             # 源代码目录
│   ├── api/                         # API 接口定义
│   │   ├── index.ts                 # 主接口（数据统计、报表）
│   │   ├── employee.ts              # 员工相关接口
│   │   ├── category.ts              # 分类相关接口
│   │   ├── dish.ts                  # 菜品相关接口
│   │   ├── setMeal.ts               # 套餐相关接口
│   │   ├── order.ts                 # 订单相关接口
│   │   ├── charts.ts                # 图表数据接口
│   │   ├── users.ts                 # 用户相关接口
│   │   └── inform.ts                # 通知相关接口
│   │
│   ├── assets/                      # 静态资源（会被 webpack 处理）
│   │   ├── icons/                   # 图标资源
│   │   ├── login/                   # 登录页相关图片
│   │   ├── 404-images/              # 404 页面图片
│   │   ├── *.mp3                    # 音频文件（订单提醒）
│   │   └── *.png                    # 通用图片
│   │
│   ├── components/                  # 全局公共组件
│   │   ├── Breadcrumb/              # 面包屑导航
│   │   ├── Charts/                  # 图表组件（柱状图、折线图、混合图）
│   │   ├── Empty/                   # 空状态组件
│   │   ├── Hamburger/               # 侧边栏折叠按钮
│   │   ├── HeadLable/               # 页面标题组件
│   │   ├── ImgUpload/               # 图片上传组件
│   │   └── InputAutoComplete/       # 自动完成输入框
│   │
│   ├── icons/                       # SVG 图标
│   │   ├── svg/                     # SVG 源文件
│   │   └── components/              # SVG 组件（自动生成）
│   │
│   ├── layout/                      # 布局组件
│   │   ├── index.vue                # 主布局容器
│   │   ├── components/
│   │   │   ├── AppMain.vue          # 主内容区域
│   │   │   ├── Navbar/              # 顶部导航栏
│   │   │   └── Sidebar/             # 侧边栏
│   │   └── mixin/
│   │       └── resize.ts            # 响应式布局 mixin
│   │
│   ├── store/                       # Vuex 状态管理
│   │   ├── index.ts                 # Store 入口
│   │   └── modules/
│   │       ├── app.ts               # 应用全局状态
│   │       └── user.ts              # 用户状态
│   │
│   ├── styles/                      # 全局样式
│   │   ├── index.scss               # 样式入口
│   │   ├── element-variables.scss   # Element UI 主题定制
│   │   ├── newRJWMsystem.scss       # 瑞吉外卖系统样式
│   │   ├── sidebar.scss             # 侧边栏样式
│   │   ├── home.scss                # 首页样式
│   │   ├── _variables.scss          # SCSS 变量
│   │   ├── _mixins.scss             # SCSS 混合宏
│   │   ├── _transition.scss         # 过渡动画
│   │   ├── _svgicon.scss            # SVG 图标样式
│   │   └── icon/                    # 字体图标
│   │
│   ├── utils/                       # 工具函数
│   │   ├── request.ts               # Axios 请求封装
│   │   ├── requestOptimize.ts       # 请求去重优化
│   │   ├── cookies.ts               # Cookie 操作封装
│   │   ├── validate.ts              # 表单验证规则
│   │   ├── formValidate.ts          # 表单验证方法
│   │   └── common.ts                # 通用工具函数
│   │
│   ├── views/                       # 页面视图
│   │   ├── login/                   # 登录页
│   │   ├── dashboard/               # 工作台
│   │   ├── employee/                # 员工管理
│   │   ├── category/                # 分类管理
│   │   ├── dish/                    # 菜品管理
│   │   ├── setmeal/                 # 套餐管理
│   │   ├── orderDetails/            # 订单管理
│   │   ├── statistics/              # 数据统计
│   │   ├── chart/                   # 图表页面
│   │   ├── inform/                  # 通知中心
│   │   └── 404.vue                  # 404 页面
│   │
│   ├── App.vue                      # 根组件
│   ├── main.ts                      # 应用入口文件
│   ├── router.ts                    # 路由配置
│   ├── permission.ts                # 路由权限控制
│   ├── config.json                  # 应用配置（图片服务器地址等）
│   ├── shims-vue.d.ts               # Vue 类型声明
│   └── registerServiceWorker.ts     # PWA Service Worker
│
├── tests/                           # 测试文件
│   └── unit/                        # 单元测试
│       ├── components/              # 组件测试
│       └── utils/                   # 工具函数测试
│
├── .browserslistrc                  # 浏览器兼容性配置
├── .editorconfig                    # 编辑器配置
├── babel.config.js                  # Babel 配置
├── cypress.json                     # Cypress E2E 测试配置
├── jest.config.js                   # Jest 单元测试配置
├── postcss.config.js                # PostCSS 配置
├── tsconfig.json                    # TypeScript 配置
├── vue.config.js                    # Vue CLI 配置（代理、打包等）
├── Dockerfile                       # Docker 容器配置
├── package.json                     # 项目依赖配置
└── README.md                        # 项目说明文档
```

---

## 🚀 快速开始

### 环境要求

- **Node.js**: >= 10.x
- **npm**: >= 6.x 或 **yarn**: >= 1.x

### 安装依赖

```bash
# 使用 npm
npm install

# 或使用 yarn（推荐）
yarn install
```

### 启动开发服务器

```bash
# 使用 npm
npm run serve

# 或使用 yarn
yarn serve
```

启动成功后，浏览器会自动打开 `http://localhost:8081`

### 构建生产环境

```bash
# 生产环境打包（去除删除功能）
npm run build
# 或
yarn build

# 测试环境打包（保留删除功能）
npm run build:uat
# 或
yarn build:uat
```

打包完成后，生成的静态文件在 `dist/` 目录下。

### 代码检查

```bash
npm run lint
# 或
yarn lint
```

### 运行测试

```bash
# 单元测试
npm run test:unit

# E2E 测试
npm run test:e2e
```

---

## ⚙️ 环境配置

### 1. 配置后端接口地址

在项目根目录创建或修改 `.env` 文件：

```env
# 开发环境
VUE_APP_BASE_API = '/api'
VUE_APP_URL = 'http://localhost:8080'
```

### 2. 配置图片服务器地址

修改 `src/config.json` 文件：

```json
{
  "baseUrl": "http://your-server-address:8200"
}
```

> **注意**: 部署到生产环境时，需要将 `baseUrl` 修改为实际的服务器地址。

### 3. 开发服务器代理配置

在 `vue.config.js` 中已配置代理，将 `/api` 开头的请求转发到后端服务器：

```javascript
proxy: {
  '/api': {
    target: process.env.VUE_APP_URL,  // 后端服务地址
    changeOrigin: true,
    pathRewrite: {
      '^/api': ''
    }
  }
}
```

---

## 📚 功能模块详解

### 🔐 登录认证

- **技术实现**：
  - 基于 Token 的身份认证
  - 使用 js-cookie 存储 Token
  - MD5 加密用户密码
  - 路由守卫控制页面访问权限

- **登录流程**：
  1. 用户输入用户名和密码
  2. 前端使用 MD5 对密码加密
  3. 调用登录接口，获取 Token
  4. 将 Token 存储到 Cookie
  5. 跳转到工作台页面

### 📊 工作台

- **今日数据概览**：
  - 营业额统计
  - 有效订单数
  - 订单完成率
  - 平均客单价
  - 新增用户数

- **订单管理概览**：
  - 待接单数量
  - 待派送数量
  - 派送中数量

- **菜品总览**：
  - 已启售菜品数
  - 已停售菜品数

- **套餐总览**：
  - 已启售套餐数
  - 已停售套餐数

### 👥 员工管理

- **列表功能**：
  - 分页展示员工信息
  - 按员工姓名搜索
  - 显示账号、姓名、手机号、状态、操作时间

- **操作功能**：
  - 新增员工（姓名、用户名、手机号、性别、身份证号）
  - 编辑员工信息
  - 启用/禁用员工账号
  - 查看员工详情

### 📂 分类管理

- **列表功能**：
  - 分页展示分类信息
  - 按分类名称搜索
  - 按分类类型筛选（菜品分类/套餐分类）
  - 显示分类名称、类型、排序、状态、操作时间

- **操作功能**：
  - 新增分类（名称、类型、排序）
  - 修改分类信息
  - 启用/禁用分类
  - 删除分类（需验证是否关联菜品/套餐）

### 🍜 菜品管理

- **列表功能**：
  - 分页展示菜品信息
  - 按菜品名称搜索
  - 按菜品分类筛选
  - 按售卖状态筛选（起售/停售）
  - 显示菜品图片、名称、分类、价格、售卖状态、操作时间

- **操作功能**：
  - 新增菜品（名称、分类、价格、图片、描述、口味）
  - 修改菜品信息
  - 起售/停售单个菜品
  - 批量起售/停售
  - 删除菜品

- **特色功能**：
  - 图片上传（支持图片预览）
  - 口味配置（辣度、温度、忌口等）
  - 新增菜品默认为停售状态

### 🍱 套餐管理

- **列表功能**：
  - 分页展示套餐信息
  - 按套餐名称搜索
  - 按套餐分类筛选
  - 按售卖状态筛选（起售/停售）
  - 显示套餐图片、名称、分类、价格、售卖状态、操作时间

- **操作功能**：
  - 新增套餐（名称、分类、价格、图片、描述、关联菜品）
  - 修改套餐信息
  - 起售/停售单个套餐
  - 批量起售/停售
  - 删除套餐

- **特色功能**：
  - 图片上传（支持图片预览）
  - 关联菜品选择器
  - 套餐菜品份数配置
  - 新增套餐默认为停售状态

### 📦 订单管理

- **订单状态分类**：
  - 全部订单
  - 待接单
  - 待派送
  - 派送中
  - 已完成
  - 已取消

- **列表功能**：
  - 按订单状态 Tab 切换
  - 按订单号搜索
  - 按手机号搜索
  - 按下单时间筛选
  - 显示订单号、状态、用户、手机号、地址、金额、下单时间

- **操作功能**：
  - 查看订单详情（订单信息、收货人信息、菜品明细）
  - 接单（待接单 → 待派送）
  - 拒单（待接单 → 已取消，需填写拒单原因）
  - 派送（待派送 → 派送中）
  - 完成（派送中 → 已完成）
  - 取消订单（需填写取消原因）

- **特色功能**：
  - 新订单语音播报提醒
  - 订单状态实时更新
  - 订单数量徽章显示

### 📈 数据统计

#### 营业额统计
- 选择时间范围查看营业额趋势
- 折线图展示每日/每周/每月营业额
- 支持今日、近7日、近30日快捷选择

#### 用户统计
- 用户总量和新增用户趋势
- 折线图展示用户增长情况
- 支持自定义时间范围

#### 订单统计
- 订单总数和有效订单数
- 订单完成率统计
- 支持订单状态分布饼图

#### 销量排名 TOP10
- 热销菜品/套餐排行榜
- 柱状图展示销量对比
- 支持按时间范围筛选

#### 数据导出
- 支持导出运营数据报表
- Excel 格式，包含完整统计数据

---

## 💻 开发指南

### 代码规范

本项目使用 ESLint + TypeScript Standard 代码规范，在提交代码前请确保：

1. 代码通过 ESLint 检查：`npm run lint`
2. 遵循 TypeScript 类型规范
3. 组件使用 Class Component 装饰器语法
4. API 接口统一在 `src/api/` 目录定义

### 组件开发规范

```typescript
import { Component, Vue } from 'vue-property-decorator'

@Component({
  name: 'ComponentName'
})
export default class ComponentName extends Vue {
  // 数据属性
  private message: string = 'Hello'
  
  // 计算属性
  get computedValue() {
    return this.message
  }
  
  // 方法
  private handleClick() {
    // ...
  }
  
  // 生命周期
  created() {
    // ...
  }
}
```

### API 接口调用

```typescript
import { getEmployeeList } from '@/api/employee'

async fetchData() {
  try {
    const { data } = await getEmployeeList({ page: 1, pageSize: 10 })
    console.log(data)
  } catch (error) {
    console.error(error)
  }
}
```

### Vuex 使用

```typescript
import { Component, Vue } from 'vue-property-decorator'
import { UserModule } from '@/store/modules/user'

@Component
export default class Example extends Vue {
  get username() {
    return UserModule.username
  }
  
  logout() {
    UserModule.Logout()
  }
}
```

### 路由配置

```typescript
{
  path: '/example',
  component: Layout,
  children: [
    {
      path: 'index',
      component: () => import('@/views/example/index.vue'),
      meta: {
        title: '示例页面',
        icon: 'icon-example'
      }
    }
  ]
}
```

### 新增页面流程

1. 在 `src/views/` 下创建页面组件
2. 在 `src/router.ts` 中配置路由
3. 在 `src/api/` 下创建对应的接口文件（如需要）
4. 开发页面功能
5. 测试功能是否正常

### 图片上传

项目使用自定义的 `ImgUpload` 组件：

```vue
<template>
  <ImgUpload
    v-model="imageUrl"
    :action="uploadUrl"
  />
</template>

<script>
import ImgUpload from '@/components/ImgUpload/index.vue'

export default {
  components: { ImgUpload },
  data() {
    return {
      imageUrl: '',
      uploadUrl: '/common/upload'
    }
  }
}
</script>
```

### ECharts 图表使用

```typescript
import { Component, Vue } from 'vue-property-decorator'

@Component
export default class ChartExample extends Vue {
  mounted() {
    this.initChart()
  }
  
  private initChart() {
    const chart = this.$echarts.init(this.$refs.chart as HTMLElement)
    chart.setOption({
      title: { text: '示例图表' },
      xAxis: { type: 'category', data: ['Mon', 'Tue', 'Wed'] },
      yAxis: { type: 'value' },
      series: [{ data: [120, 200, 150], type: 'line' }]
    })
  }
}
```

---

## 📝 版本迭代记录

### v1.3（最新版本）

**开发人员**: 司文强

**迭代内容**:
- ✅ **订单管理模块**
  - 新增订单状态切换 Tab（全部、待接单、待派送、派送中、已完成、已取消）
  - 新增订单列表字段和操作按钮（派送、接单、拒单、取消、完成）
  - 新增订单详情页面（订单信息、收货人信息、菜品明细）
  - 新增订单语音播报功能（新订单实时提醒）
  - 优化订单搜索和筛选功能

### v1.2

**开发人员**: 司文强

**迭代内容**:
- ✅ **员工管理优化**
  - 加入修改时间字段
  - 状态文案由"正常"改为"启用"
  - 增加查询按钮
  
- ✅ **分类管理优化**
  - 搜索条件增加名称和类型筛选
  - 加入状态字段
  - 增加启用、禁用功能
  
- ✅ **菜品管理优化**
  - 搜索条件增加菜品分类筛选
  - 搜索条件增加售卖状态筛选
  - 增加查询按钮
  - 新增菜品默认为禁用状态
  
- ✅ **套餐管理优化**
  - 搜索条件增加套餐分类筛选
  - 搜索条件增加售卖状态筛选
  - 增加查询按钮
  - 新增套餐默认为禁用状态
  
- ✅ **其他优化**
  - 根据设计稿调整页面样式和交互
  - 修复以上 4 个模块的 Bug 和问题

### v1.0

**基础功能**:
- ✅ 用户登录/登出
- ✅ 工作台数据概览
- ✅ 员工管理基础功能
- ✅ 分类管理基础功能
- ✅ 菜品管理基础功能
- ✅ 套餐管理基础功能
- ✅ 数据统计基础功能

