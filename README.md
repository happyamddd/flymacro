# FlyMacro - 魔兽世界宏库

基于 Hugo + Cloudflare Pages 构建的合法 UI 宏/插件下载站。

## 技术栈

- **Hugo** - 静态网站生成器
- **Cloudflare Pages** - 免费托管 + 全球 CDN
- **Decap CMS** - 可视化内容管理后台
- **Netlify Identity** - 免费用户认证

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
│   └── admin/            # Decap CMS 后台
└── hugo.toml             # 站点配置
```

## 内容管理

### 方式一：VSCode + Git（推荐）

直接在 `content/zh/` 目录下编辑 Markdown 文件，提交后 Cloudflare Pages 自动构建。

### 方式二：Decap CMS 网页后台

访问 `https://你的域名/admin/`，使用 Netlify Identity 登录后可视化编辑内容。

**注意**：使用后台前需要先配置 Netlify Identity（见下方部署说明）。

## 部署到 Cloudflare Pages

1. 在 GitHub 创建仓库，推送代码
2. 登录 [dash.cloudflare.com](https://dash.cloudflare.com)
3. Pages → 创建项目 → 连接 GitHub 仓库
4. 构建设置：
   - Build command: `hugo`
   - Build output directory: `public`
   - 环境变量: `HUGO_VERSION` = `0.152.2`
5. 保存并部署

## 配置 Decap CMS（可选）

1. 在 [netlify.com](https://netlify.com) 注册免费账号
2. 创建一个新站点（只用于 Identity，不需要真正部署）
3. Site settings → Identity → Enable Identity
4. Identity → Settings → Registration → Invite only（推荐）
5. Identity → Services → Git Gateway → Enable Git Gateway
6. 复制 Git Gateway 的 Site domain
7. 修改 `static/admin/config.yml` 中的 `backend.site_domain`
8. 提交并推送，等待 Cloudflare Pages 重新构建

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
