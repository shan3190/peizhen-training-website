# 陪诊师培训网站 - 部署指南

## 项目概述

这是一个专业的陪诊师在线培训网站，采用单页应用设计，包含首页、课程介绍、题库展示等核心模块。使用 HTML + Tailwind CSS 实现，支持响应式移动端适配。

### 网站功能

- ✅ 响应式设计，完美适配移动端和桌面端
- ✅ 首页英雄区域，展示平台核心价值
- ✅ 数据统计展示，突出平台优势
- ✅ 6门核心课程展示卡片
- ✅ 核心优势功能模块
- ✅ 在线题库预览（150道题）
- ✅ 联系表单区域
- ✅ 平滑滚动和导航效果

---

## 部署方式一：Vercel 快速部署（推荐）

### 前置准备

1. 拥有一个 GitHub 账号
2. 拥有一个 Vercel 账号（可使用 GitHub 账号登录）

### 详细步骤

#### 第一步：创建 GitHub 仓库

1. 登录 GitHub，点击右上角的 **+** 号 → **New repository**
2. 填写仓库信息：
   - **Repository name**: `peizhen-training-website`（或其他名称）
   - **Description**: `陪诊师培训网站`
   - 选择 **Public**（公开仓库）
   - 勾选 **Add a README file**（可选）
   - 点击 **Create repository**

#### 第二步：上传网站文件

**方式A：使用网页直接上传**

1. 在仓库页面，点击 **Add file** → **Upload files**
2. 将 `index.html` 文件拖拽到上传区域
3. 填写提交信息：`Add website files`
4. 点击 **Commit changes**

**方式B：使用 Git 命令行**

```bash
# 克隆仓库
git clone https://github.com/你的用户名/peizhen-training-website.git

# 进入仓库目录
cd peizhen-training-website

# 将 index.html 复制到该目录
# 然后提交
git add index.html
git commit -m "Add website files"
git push
```

#### 第三步：连接 Vercel 并部署

1. 访问 [Vercel 官网](https://vercel.com/) 并登录
2. 点击 **Add New...** → **Project**
3. 在 **Import Git Repository** 区域，找到刚才创建的仓库，点击 **Import**
4. 配置项目：
   - **Project Name**: 保持默认或修改
   - **Framework Preset**: 选择 `Other`
   - **Root Directory**: 保持默认（./）
   - **Build and Output Settings**: 保持默认
5. 点击 **Deploy** 按钮
6. 等待约 1-2 分钟，部署完成！

#### 第四步：获取部署链接

部署完成后，Vercel 会自动生成一个访问链接，格式类似：
- `https://peizhen-training-website.vercel.app`

你可以在项目控制台看到这个链接，点击即可访问网站。

---

## 部署方式二：绑定自定义域名（zzpzt.cn）

### 步骤

1. 在 Vercel 项目控制台，点击 **Settings** → **Domains**
2. 输入你的域名：`zzpzt.cn`
3. 点击 **Add**
4. Vercel 会提供 DNS 配置信息：
   - **Nameservers**:
     - `ns1.vercel-dns.com`
     - `ns2.vercel-dns.com`

5. 登录你的域名注册商（火山引擎）控制台
6. 找到域名管理 → DNS 管理/域名解析
7. 修改域名的 Nameserver（DNS服务器）为 Vercel 提供的地址
8. 等待 DNS 生效（可能需要几小时）
9. DNS 生效后，Vercel 会自动配置 SSL 证书
10. 你的网站就可以通过 `https://zzpzt.cn` 访问了！

---

## 本地开发预览

### 使用简单 HTTP 服务器

```bash
# 使用 Python
python3 -m http.server 8000

# 使用 Node.js (需要安装 http-server)
npx http-server -p 8000

# 使用 PHP
php -S localhost:8000
```

然后在浏览器访问 `http://localhost:8000`

---

## 文件结构

```
陪诊师培训网站/
├── index.html                          # 网站主文件
├── README.md                           # 部署指南（本文件）
├── 陪诊师培训网站需求分析与功能设计文档.md
├── 陪诊师培训平台开发规划文档.md
└── 考试题库模板.md
```

---

## 技术栈

- **HTML5**: 语义化标签
- **Tailwind CSS v3**: 快速构建现代网站
- **Font Awesome 4.7**: 图标库
- **Vanilla JavaScript**: 原生 JS，无需框架
- **CDN 资源**: 所有外部资源均使用 CDN，无需本地依赖

---

## Vercel 优势

为什么选择 Vercel 部署：

1. ✅ **免费额度**：个人使用完全免费
2. ✅ **无需备案**：域名在火山引擎购买，使用 Vercel 托管无需备案
3. ✅ **自动 HTTPS**: 自动配置 SSL 证书
4. ✅ **全球 CDN**: 网站访问速度快
5. ✅ **自动部署**: 每次推送到 GitHub 自动更新网站
6. ✅ **零配置**: 简单几步即可完成部署

---

## 常见问题

### Q: 部署后网站无法访问？

A: 请检查：
1. 文件是否正确上传到 GitHub 仓库
2. Vercel 部署是否成功（查看部署日志）
3. 域名 DNS 是否正确配置（如使用自定义域名）

### Q: 如何更新网站内容？

A: 只需修改 GitHub 仓库中的 `index.html` 文件并提交，Vercel 会自动重新部署。

### Q: Vercel 免费版有限制吗？

A: 免费版包含：
- 无限站点
- 每月 100GB 带宽
- 自动 HTTPS
- 全球 CDN
对于普通培训网站完全够用

### Q: 可以添加后端功能吗？

A: 可以！Vercel 支持 Serverless Functions，可以添加：
- 用户注册登录
- 在线考试系统
- 学习进度追踪
- 证书生成等功能

---

## 下一步建议

1. ✅ 完成 GitHub + Vercel 部署
2. ✅ 绑定自定义域名 zzpzt.cn
3. ⏳ 添加用户注册登录功能
4. ⏳ 开发在线考试系统
5. ⏳ 添加学习进度追踪
6. ⏳ 集成视频课程播放

---

## 联系支持

如有部署问题，请参考：
- [Vercel 官方文档](https://vercel.com/docs)
- [GitHub 帮助](https://docs.github.com/)
