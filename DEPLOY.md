# GitHub Pages 部署指南

## 🚀 部署步骤

### 1. 创建GitHub仓库

1. 访问 [GitHub](https://github.com)
2. 点击右上角的 "+" 号，选择 "New repository"
3. 仓库名称建议：`chatbot` 或 `chatbot-website`
4. 选择 "Public"（公开）
5. 不要勾选 "Add a README file"（我们已经有了）
6. 点击 "Create repository"

### 2. 上传代码到GitHub

在本地终端执行以下命令：

```bash
# 添加远程仓库（替换 YOUR_USERNAME 为您的GitHub用户名）
git remote add origin https://github.com/YOUR_USERNAME/chatbot.git

# 推送代码到GitHub
git push -u origin main
```

### 3. 启用GitHub Pages

1. 在GitHub仓库页面，点击 "Settings" 标签
2. 在左侧菜单中找到 "Pages"
3. 在 "Source" 部分，选择 "Deploy from a branch"
4. 在 "Branch" 下拉菜单中选择 "main"
5. 点击 "Save"

### 4. 等待部署完成

- GitHub Pages 通常需要几分钟时间部署
- 部署完成后，您会看到一个绿色的勾号
- 您的网站地址将是：`https://YOUR_USERNAME.github.io/chatbot`

## 🔧 自动部署（可选）

如果您想要自动部署，可以：

1. 在仓库设置中启用 GitHub Actions
2. 每次推送到 main 分支时，网站会自动更新

## 📝 注意事项

- 确保 `index.html` 文件在仓库根目录
- 网站是公开的，任何人都可以访问
- 如果需要私有仓库，需要升级到GitHub Pro

## 🎯 测试

部署完成后，访问您的GitHub Pages URL测试功能：

- 检查全屏布局是否正常
- 测试快捷键按钮功能
- 验证响应式设计在不同设备上的表现

---

**提示**: 如果遇到问题，请检查GitHub仓库的Actions标签页查看部署日志。 