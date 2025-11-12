# Fresh Demo

一个基于 [Fresh](https://fresh.deno.dev/) 框架的 Deno 全栈 Web 应用示例项目。Fresh 是一个为 Deno 设计的现代 Web 框架，支持 Islands 架构和零配置。

## 技术栈

- **Deno**: 最新版本
- **Fresh**: 2.1.3+
- **Preact**: 10.27.2
- **Vite**: 7.1.3
- **Tailwind CSS**: 4.1.10
- **DaisyUI**: 5.3.9

## 项目结构

```
fresh-demo/
├── routes/              # 基于文件系统的路由
│   └── ...
├── islands/             # 交互式 Islands 组件
│   └── ...
├── components/          # 共享组件
│   └── ...
├── static/              # 静态资源
├── main.ts              # 应用入口和配置
├── deno.json            # Deno 配置
├── vite.config.ts       # Vite 配置
└── README.md
```

## 功能特性

- Islands 架构（部分水合）
- 基于文件系统的路由
- 服务端渲染 (SSR)
- 零配置设置
- TypeScript 支持
- Tailwind CSS 集成
- 热重载开发体验

## 快速开始

### 前置要求

- [Deno](https://deno.com/) 最新版本

### 安装和运行

```bash
# 运行开发服务器
deno task dev
# 或
deno task start
```

应用将在 `http://localhost:8000` 启动。

### 构建和部署

```bash
# 构建生产版本
deno task build

# 启动生产服务器
deno task start

# 代码检查
deno task check
```

## 项目特点

### Islands 架构

Fresh 使用 Islands 架构：
- 默认服务端渲染
- 只对交互式组件进行客户端水合
- 更小的 JavaScript 包
- 更快的初始加载

### 路由系统

基于文件系统的路由：
- `routes/` 目录定义路由
- 自动处理动态路由
- 支持中间件
- API 路由支持

### 示例路由

- **`/api/:name`**: API 路由示例
- **`/api2/:name`**: 程序化定义的路由

## 开发

### 热重载

Fresh 提供快速刷新功能，修改代码会自动更新。

### 中间件

支持中间件系统：

```typescript
app.use(async (ctx) => {
  ctx.state.shared = "hello";
  return await ctx.next();
});
```

### 静态文件

静态文件服务：

```typescript
app.use(staticFiles());
```

## 代码说明

### 主应用 (`main.ts`)

应用配置包括：
- 静态文件服务
- 中间件定义
- 路由注册
- 文件系统路由集成

### Islands

交互式组件放在 `islands/` 目录：
- 只在客户端运行
- 自动水合
- 支持 Preact Hooks

### 组件

共享组件放在 `components/` 目录：
- 服务端和客户端都可以使用
- 支持 JSX/TSX

## 部署

### Deno Deploy（推荐）

Fresh 应用可以一键部署到 Deno Deploy：

```bash
# 使用 Deno Deploy CLI
deployctl deploy --project=your-project
```

### 其他平台

- Docker
- 自托管服务器
- 任何支持 Deno 的平台

## 优势

### 性能

- 零 JavaScript 默认（Islands 架构）
- 快速的服务端渲染
- 优化的资源加载

### 开发体验

- 零配置
- TypeScript 原生支持
- 快速反馈循环
- 现代化工具链

## 参考资源

- [Fresh 官方网站](https://fresh.deno.dev/)
- [Fresh 文档](https://fresh.deno.dev/docs)
- [Deno 文档](https://deno.com/manual)
- [Preact 文档](https://preactjs.com/)
