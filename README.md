# FlyMacro - 魔兽世界宏库

基于 Hugo + Cloudflare Pages 构建的合法 UI 宏/插件下载站。

## 技术栈

- **Hugo** - 静态网站生成器
- **Cloudflare Pages** - 免费托管 + 全球 CDN
- **本地生成工具** - `tools/macro-generator.html` 浏览器表单生成 Markdown

## 本地开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npx hugo server -D

# 构建
npx hugo
```

## 项目结构

```
flymacro/
├── archetypes/           # 内容模板
├── content/zh/           # 中文内容
│   ├── macros/           # 宏包（免费/付费）
│   ├── pages/            # 独立页面
│   ├── guide/            # 教程
│   └── blog/             # 公告
├── layouts/              # 页面模板
├── static/               # 静态资源
│   ├── downloads/        # 免费下载文件
│   ├── images/           # 图片
│   └── admin/            # Decap CMS 后台（已废弃）
├── tools/                # 本地辅助工具
│   └── macro-generator.html  # 宏包 Markdown 生成器（双击使用）
└── hugo.toml             # 站点配置
```

## 内容管理

### 方式一：本地宏包生成工具（推荐，最简单）

双击打开 `tools/macro-generator.html`，通过下拉选项填写表单：

1. **基础信息**：选择职业（13个职业下拉选项）、版本（下拉选项）、类型（免费/付费）
2. **型号定价**（仅付费宏）：点击"+ 添加型号"，填写名称、价格、功能、购买链接
3. **内容描述**：填写功能介绍、适用场景、使用说明
4. 点击 **"生成 Markdown"**，然后 **"复制到剪贴板"**
5. 在 VSCode 中新建文件，粘贴内容，保存到 `content/zh/macros/free/` 或 `content/zh/macros/premium/`
6. 提交到 GitHub，Cloudflare Pages 自动构建发布

### 方式二：VSCode 直接编辑

直接在 `content/zh/` 目录下编辑 Markdown 文件，提交后 Cloudflare Pages 自动构建。

新建宏包时，可以复制已有文件作为模板，或使用 `archetypes/macro.md` 作为参考。

### 方式三：Decap CMS 网页后台（已废弃，不建议使用）

由于 Netlify Identity 在 Cloudflare Pages 上的兼容性问题，Decap CMS 后台已废弃。请使用方式一或方式二。

## 部署到 Cloudflare Pages

1. 在 GitHub 创建仓库，推送代码
2. 登录 [dash.cloudflare.com](https://dash.cloudflare.com)
3. Pages → 创建项目 → 连接 GitHub 仓库
4. 构建设置：
   - Build command: `hugo`
   - Build output directory: `public`
   - 环境变量: `HUGO_VERSION` = `0.152.2`
5. 保存并部署

## 添加新宏包（快速步骤）

1. 双击 `tools/macro-generator.html`，在浏览器中打开
2. 填写表单（职业、专精、版本都从下拉选项中选择）
3. 点击"生成 Markdown" → "复制到剪贴板"
4. 在 VSCode 中，在 `content/zh/macros/free/` 或 `content/zh/macros/premium/` 目录下新建文件
5. 文件名格式：`职业-专精-描述.md`（如：`priest-shadow-dps.md`）
6. 粘贴内容，保存
7. Git 提交并推送：

```bash
git add content/zh/macros/
git commit -m "添加：牧师暗影输出宏"
git push origin main
```

Cloudflare Pages 会自动构建并发布。

## 多语言

当前仅启用中文。后续添加英文/韩文/日文时：

1. 在 `hugo.toml` 中启用对应语言配置
2. 创建 `content/en/`, `content/ko/`, `content/ja/` 目录
3. 翻译内容

## 域名绑定

Cloudflare Pages 项目创建后：

1. Pages 项目 → 自定义域 → 设置自定义域
2. 输入 `flymacro.qzz.io`
3. 根据提示在你的域名提供商处添加 CNAME 记录
4. 等待 DNS 生效（通常几分钟到几小时）

如果无法控制 `qzz.io` 的 DNS，请使用 Cloudflare Pages 提供的默认域名（如 `flymacro.pages.dev`）。
