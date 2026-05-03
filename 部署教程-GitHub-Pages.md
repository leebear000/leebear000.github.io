# GitHub Pages 部署个人主页 - 详细教程

> 目标：把你的个人主页网站免费部署到互联网上，让任何人都能访问

---

## 前置条件

- 一个 GitHub 账号（免费注册）
- 你的个人主页网站文件（已准备好）

---

## 第一步：注册/登录 GitHub

1. 打开 [github.com](https://github.com)
2. 点击右上角 **Sign up** 注册（如果已有账号直接 Sign in）
3. 按提示完成注册（邮箱验证等）

---

## 第二步：创建仓库（Repository）

1. 登录后，点击右上角 **+** 号 → **New repository**

2. 填写仓库信息：
   - **Repository name**: `你的用户名.github.io`
     - ⚠️ **重要**：必须把 `你的用户名` 换成你的 GitHub 用户名！
     - 例如：如果你的 GitHub 用户名是 `yangzhe`，就填 `yangzhe.github.io`
   - **Description**: 个人主页（可选）
   - **Public** ✓（必须选公开，GitHub Pages 免费版只支持公开仓库）
   - **Add a README file**: 不勾选

3. 点击底部 **Create repository**

   ![创建仓库示意图]

---

## 第三步：上传网站文件

### 方法一：网页直接上传（最简单）

1. 进入刚创建的仓库页面
2. 点击 **Add file** → **Upload files**
3. 把本地 `personal-site` 文件夹里的所有文件拖进网页：
   ```
   personal-site/
   ├── index.html
   ├── css/
   │   └── style.css
   ├── js/
   │   └── main.js
   └── images/
       └── (你的照片)
   ```
4. 注意：要上传的是文件夹**里面的内容**，不是整个文件夹
5. 在下方填写提交信息：
   - Commit changes: `Initial commit - personal website`
6. 点击 **Commit changes**

### 方法二：用 Git 命令行上传（适合后续更新）

```bash
# 1. 进入你的网站文件夹
cd personal-site

# 2. 初始化 Git 仓库
git init

# 3. 添加所有文件
git add .

# 4. 提交
git commit -m "Initial commit - personal website"

# 5. 关联远程仓库（把下面 URL 换成你的）
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git

# 6. 推送
git push -u origin main
```

---

## 第四步：开启 GitHub Pages

1. 在仓库页面，点击顶部 **Settings** 标签
2. 左侧菜单找到 **Pages**（在 Code and automation 下面）
3. 在 **Build and deployment** 部分：
   - **Source**: 选择 **Deploy from a branch**
   - **Branch**: 选择 `main` / `master`，文件夹选 `/(root)`
4. 点击 **Save**

   ![Pages 设置示意图]

---

## 第五步：等待部署完成

1. 回到仓库主页，点击上方的 **Actions** 标签
2. 你会看到有一个工作流在运行（黄色圆点）
3. 等待 1-3 分钟，变成绿色勾号 ✅ 就表示部署成功了

---

## 第六步：访问你的网站！

打开浏览器，访问：

```
https://你的用户名.github.io
```

例如：`https://yangzhe.github.io`

🎉 你的个人主页现在全世界都能访问了！

---

## 后续更新网站

当你修改了网站内容（比如换照片、改文字），需要重新上传：

### 网页方式：
1. 进入仓库 → 找到要修改的文件
2. 点击文件 → 点击右上角铅笔图标 ✏️ 编辑
3. 修改后拉到最下面点击 **Commit changes**

### Git 方式：
```bash
cd personal-site
git add .
git commit -m "更新内容描述"
git push
```

等待 1-2 分钟，网站会自动更新。

---

## 常见问题

### Q: 访问网站显示 404？
- 检查仓库名是否和用户名完全一致（大小写也要一样）
- 确认 index.html 在仓库根目录
- 等待 5-10 分钟再刷新

### Q: 怎么绑定自己的域名？
1. 买个域名（阿里云/腾讯云，约 ¥30-60/年）
2. 在仓库 Settings → Pages → Custom domain 填入你的域名
3. 在域名管理后台添加 CNAME 记录：
   - 主机记录：`www` 或 `@`
   - 记录值：`你的用户名.github.io`

### Q: 网站加载慢？
- GitHub Pages 在国外，国内访问可能稍慢
- 解决方案：用 Vercel 部署（国内访问更快，也是免费的）

### Q: 图片不显示？
- 检查图片路径是否正确（相对路径 `./images/xxx.jpg`）
- 确认图片已上传到仓库
- 图片文件名不要有中文或空格

---

## 进阶：自定义域名 + HTTPS

GitHub Pages 自动提供 HTTPS（网址前面有小锁 🔒），非常安全。

如果你绑定了自定义域名：
1. 在 Pages 设置里勾选 **Enforce HTTPS**
2. 等待几分钟证书自动生效

---

## 总结流程图

```
注册 GitHub → 创建仓库（用户名.github.io）→ 上传文件 → 开启 Pages → 等待部署 → 访问网站
     ↑                                                                            ↓
     └──────────────────── 后续更新时重新上传文件 ←────────────────────────────────┘
```

---

**祝你部署顺利！有问题随时问我。** 🚀
