# iCSS 网站

基于 GitHub 上的 iCSS 仓库构建的现代化网站，展示 CSS 奇技淫巧。

## 功能特性

### 🎨 主题切换
- **亮色主题**: 适合日间使用
- **暗色主题**: 适合夜间使用，护眼
- **跟随系统**: 自动跟随系统主题设置
- **持久化**: 主题选择会保存到本地存储

### 🌍 多语言支持
- **中文**: 简体中文界面
- **English**: 英文界面
- **持久化**: 语言选择会保存到本地存储

### 📱 响应式设计
- 支持桌面端、平板和移动端
- 自适应布局，提供最佳用户体验

### 🎯 核心功能
- **文章列表**: 展示所有 CSS 技巧文章
- **分类筛选**: 按分类筛选文章
- **搜索功能**: 支持文章标题搜索
- **文章详情**: 完整的文章内容展示
- **代码高亮**: 支持语法高亮的代码块
- **CodePen 集成**: 直接嵌入 CodePen 演示
- **上一篇/下一篇**: 文章导航功能

## 技术栈

- **框架**: Next.js 14 (App Router)
- **语言**: TypeScript
- **样式**: Tailwind CSS
- **状态管理**: React Context
- **动画**: Framer Motion
- **图标**: Lucide React
- **代码高亮**: react-syntax-highlighter

## 快速开始

### 安装依赖
```bash
pnpm install
```

### 启动开发服务器
```bash
pnpm dev
```

### 构建生产版本
```bash
pnpm build
```

### 启动生产服务器
```bash
pnpm start
```

## 项目结构

```
icss-website/
├── app/
│   ├── api/                 # API 路由
│   ├── article/            # 文章详情页
│   ├── components/         # 可复用组件
│   ├── contexts/           # React Context
│   ├── lib/                # 工具函数
│   ├── globals.css         # 全局样式
│   ├── layout.tsx          # 根布局
│   └── page.tsx            # 首页
├── public/                 # 静态资源
└── package.json
```

## 主题系统

### 主题配置
主题系统基于 CSS 变量和 Tailwind CSS 的暗色模式实现：

- **CSS 变量**: 定义主题色彩
- **Tailwind 配置**: 支持 `dark:` 前缀的类名
- **Context API**: 管理主题状态
- **localStorage**: 持久化主题选择

### 自定义主题
可以通过修改 `app/globals.css` 中的 CSS 变量来自定义主题色彩：

```css
:root {
  --primary: 221.2 83.2% 53.3%;
  --background: 0 0% 100%;
  /* 更多变量... */
}

.dark {
  --primary: 217.2 91.2% 59.8%;
  --background: 222.2 84% 4.9%;
  /* 更多变量... */
}
```

## 多语言系统

### 翻译文件
翻译内容定义在 `app/lib/translations.ts` 中：

```typescript
export const translations: Record<Language, Translations> = {
  zh: {
    loading: '加载中...',
    error: '错误',
    // 更多翻译...
  },
  en: {
    loading: 'Loading...',
    error: 'Error',
    // 更多翻译...
  }
};
```

### 使用翻译
在组件中使用 `useApp` hook 获取翻译函数：

```typescript
import { useApp } from '../contexts/AppContext';

function MyComponent() {
  const { t } = useApp();
  
  return <div>{t('loading')}</div>;
}
```

## API 接口

### 文章列表
```
GET /api/articles?page=1&per_page=12&category=CSS&search=关键词
```

### 文章详情
```
GET /api/articles/[id]
```

### 分类列表
```
GET /api/categories
```

## 测试页面

访问以下页面测试功能：

- **首页**: `http://localhost:3000`
- **主题语言测试**: `http://localhost:3000/test-theme-lang`
- **API 测试**: `http://localhost:3000/test-api`
- **Demo 测试**: `http://localhost:3000/test-demo`

## 部署

### Vercel 部署
1. 将代码推送到 GitHub
2. 在 Vercel 中导入项目
3. 配置环境变量（如需要）
4. 自动部署

### 其他平台
项目支持部署到任何支持 Next.js 的平台：
- Netlify
- Railway
- DigitalOcean App Platform
- 自托管服务器

## 贡献

欢迎提交 Issue 和 Pull Request！

## 许可证

MIT License 