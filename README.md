## Chatbot Web（导航版）

基于纯前端的单页应用。进入网站先显示导航页，可在两种模式间选择：

- 指令查询：嵌入指令与话术场景的聊天页面，并提供右上角“快捷键”弹窗以快速复制常用文本。
- 技术查询：嵌入技术问答与知识库场景的聊天页面，暂不提供快捷项。


### 在线资源
- 指令查询页面：[`ai-agent-1.clink.cn/chat/MwGeZYTaTtCC8IXe`](https://ai-agent-1.clink.cn/chat/MwGeZYTaTtCC8IXe)
- 技术查询页面：[`ai-agent-1.clink.cn/chat/CEClB3Et4W6FvZ8h`](https://ai-agent-1.clink.cn/chat/CEClB3Et4W6FvZ8h)


## 功能特性
- **导航首页**：首次进入显示“指令查询 / 技术查询”入口卡片。
- **全屏自适应**：`iframe` 占满视口，适配各类屏幕与安全区域。
- **黑色简约风**：深色背景、浅色文字、轻边框与柔和阴影。
- **快捷键弹窗（指令查询）**：
  - 预置可复制项：`TBS1000C`、`TBS2000B`、`MSO2`、`MDO3`、`MSO456`、`MSO/DPO70000`、`MDO3000`。
  - 一键复制到剪贴板并显示底部提示。
- **技术查询**：同布局与风格，暂不提供快捷项，显示“暂无可用快捷项”。
- **返回导航**：右上角提供“返回”按钮，随时回到导航首页。
- **可访问性**：ARIA 属性、ESC 关闭弹窗、遮罩点击关闭。


## 快速开始
1. 直接打开
   - 双击 `index.html` 用浏览器打开即可使用。
   - 如需原生剪贴板 API，建议通过本地静态服务器在安全上下文访问（见下）。
2. 使用本地静态服务器（任选其一）
   - Python 3
     ```bash
     python3 -m http.server 8080
     # 浏览器打开 http://localhost:8080/
     ```
   - Node.js（http-server）
     ```bash
     npx http-server -p 8080 -c-1
     # 浏览器打开 http://localhost:8080/
     ```


## 目录结构
```
chatbot/
  ├─ index.html      # 主页面（含导航、样式与脚本）
  └─ README.md       # 项目说明
```


## 配置与自定义
- **切换嵌入地址**：在 `index.html` 中修改脚本里的 `EMBEDS` 映射。
  - 指令查询：`EMBEDS.command`
  - 技术查询：`EMBEDS.tech`
- **配置快捷项**：在 `index.html` 中调整 `OPTIONS.command` 数组。
  - 可将元素由纯型号名替换为更完整的消息文本。
- **主题与样式**：在 `index.html` 顶部样式里调整以下 CSS 变量：
  - `--primary`、`--primary-hover`、`--surface`、`--overlay`、`--border`、`--text`


## 设计与交互
- **按钮与弹窗**：右上角包含“返回”“快捷键”两个按钮；弹窗含标题、关闭按钮、选项栅格与空态提示。
- **反馈**：复制成功会显示底部 Toast，自动消失。
- **键盘支持**：ESC 关闭弹窗。


## 兼容性与注意事项
- 支持现代浏览器（Chromium/Firefox/Safari 最新版）。
- 剪贴板写入优先使用 `navigator.clipboard.writeText`，非安全上下文自动回退到选区复制方案。
- 如需最佳复制体验，建议通过 HTTP(S) 访问，而非 `file://` 直接打开。


## 常见问题
- **如何返回选择页？**
  - 右上角点击“返回”即可回到导航首页。
- **技术查询没有快捷项？**
  - 按需求暂未配置，可在 `OPTIONS.tech` 中添加。
- **如何更换主题色？**
  - 调整 `--primary` 与 `--primary-hover` 即可。


## 部署
- 作为静态页面部署在任意静态托管上（如 Nginx、GitHub Pages、Vercel 静态托管等）。
- 确保通过 HTTP/HTTPS 访问以获得更好的剪贴板权限支持。

