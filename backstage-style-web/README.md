# Backstage Style Web Skill

## 概述

这个skill基于`backstage-style-web`目录中的企业级设计系统，帮助用户生成现代化的React网站应用。该设计系统基于Radix UI、Tailwind CSS和TypeScript构建，提供了完整的组件库和设计规范。

## 功能特性

### 🎨 设计系统
- 完整的色彩体系（11级品牌色 + 功能色）
- 响应式排版系统（Inter/Poppins字体）
- 统一的间距和阴影规范
- 支持亮色/暗色主题切换

### 🧩 组件库
- 47+ 企业级React组件
- 基于Radix UI的可访问性支持
- TypeScript类型安全
- CVA变体系统

### 📱 响应式设计
- 移动优先的设计方法
- 自适应布局组件
- 智能侧边栏（桌面折叠，移动抽屉）
- 容器查询支持

### ♿ 可访问性
- ARIA标准支持
- 键盘导航
- 屏幕阅读器兼容
- 焦点管理

## 应用类型

### 1. 管理后台 (Admin Dashboards)
- 数据可视化面板
- 用户管理系统
- 分析报告界面
- 实时监控台

### 2. 开发者工具 (Developer Tools)
- API文档界面
- 配置管理工具
- 构建和部署面板
- 团队协作平台

### 3. 数据管理应用 (Data Management)
- CRUD操作界面
- 高级筛选和搜索
- 批量操作功能
- 数据导出工具

### 4. 内容管理系统 (CMS)
- 内容创建和编辑
- 工作流程管理
- 用户权限控制
- 发布控制台

## 技术栈

```
React 18+ + TypeScript
├── UI框架: Radix UI Primitives
├── 样式: Tailwind CSS + CVA
├── 表单: React Hook Form + Zod
├── 图标: Lucide React
├── 主题: CSS Variables
└── 构建: Next.js / Vite
```

## 文件结构

```
.claude/skills/backstage-style-web/
├── SKILL.md                           # 主要skill描述
├── README.md                          # 说明文档
├── assets/
│   └── component_templates.md         # 组件模板库
├── references/
│   └── design_system_guide.md         # 设计系统指南
└── examples/
    └── admin_dashboard_example.md     # 完整示例项目
```

## 使用方法

### 1. 启用Skill
```bash
# 在Claude Code中使用
/skill backstage-style-web
```

### 2. 常见用法示例

#### 创建管理后台
```
请帮我创建一个用户管理的管理后台，需要包含：
- 用户列表和搜索功能
- 添加/编辑用户表单
- 用户状态管理
- 权限角色分配
使用Backstage style。
```

#### 创建数据分析面板
```
需要一个数据分析面板，包括：
- 关键指标卡片
- 趋势图表
- 实时数据更新
- 导出功能
使用Backstage design system。
```

#### 创建设置页面
```
帮我创建一个设置页面，包含：
- 个人资料管理
- 通知偏好设置
- 主题切换
- 安全设置
使用Backstage风格。
```

## 核心组件示例

### 页面布局
```typescript
<SidebarProvider>
  <Sidebar>
    <SidebarHeader>App Name</SidebarHeader>
    <SidebarContent>Navigation</SidebarContent>
  </Sidebar>
  <main>
    <PageLayout title="Dashboard">
      {content}
    </PageLayout>
  </main>
</SidebarProvider>
```

### 数据展示
```typescript
<Card>
  <CardHeader>
    <CardTitle>Analytics</CardTitle>
    <CardAction>
      <Button>Export</Button>
    </CardAction>
  </CardHeader>
  <CardContent>
    <DataTable data={data} />
  </CardContent>
</Card>
```

### 表单处理
```typescript
<Form {...form}>
  <FormField
    control={form.control}
    name="email"
    render={({ field }) => (
      <FormItem>
        <FormLabel>Email</FormLabel>
        <FormControl>
          <Input {...field} />
        </FormControl>
        <FormMessage />
      </FormItem>
    )}
  />
</Form>
```

## 设计原则

### 1. 一致性优先
- 统一的设计语言
- 可预测的交互模式
- 标准化的组件API

### 2. 可访问性
- 遵循WCAG 2.1标准
- 键盘和屏幕阅读器支持
- 语义化HTML结构

### 3. 性能优化
- 组件懒加载
- 代码分割
- 优化的包大小

### 4. 开发体验
- TypeScript类型安全
- 清晰的组件文档
- 一致的命名约定

## 主题配置

### 色彩系统
```css
/* 品牌色 */
--brand-500: #2B7FFF;  /* 主色 */
--brand-600: #155DFA;  /* 悬停色 */

/* 功能色 */
--success: emerald色系
--warning: amber色系
--danger: rose色系
--info: blue色系
```

### 间距系统
```css
/* 4px基础单位 */
spacing/1: 4px    /* XS */
spacing/4: 16px   /* 组件间距 */
spacing/6: 24px   /* 标准间距 */
spacing/8: 32px   /* 区块间距 */
```

## 最佳实践

### 1. 组件设计
- 优先使用复合组件模式
- 保持props接口简洁
- 支持as polymorphic属性

### 2. 样式管理
- 使用Tailwind utility classes
- CVA处理组件变体
- CSS变量支持主题切换

### 3. 状态管理
- React Hook Form处理表单
- Context API共享状态
- URL状态管理筛选器

### 4. 性能优化
- memo化昂贵组件
- 虚拟化长列表
- 代码分割路由

## 更新日志

### v1.0.0 (2025-10-29)
- ✅ 初始版本发布
- ✅ 完整的47个组件库
- ✅ 设计系统文档
- ✅ 管理后台示例
- ✅ 组件模板库
- ✅ 响应式设计支持
- ✅ 可访问性实现

## 技术支持

如果在使用过程中遇到问题：

1. 查看`references/design_system_guide.md`了解设计规范
2. 参考`assets/component_templates.md`获取组件模板
3. 查看`examples/admin_dashboard_example.md`获取完整示例
4. 确保已安装所需的依赖包

## 许可证

基于原始的backstage-style-web设计系统，遵循相同的开源许可证。