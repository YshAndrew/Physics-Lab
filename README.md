# Physics Lab · 物理实验室


![GitHub Pages](https://img.shields.io/badge/hosted%20on-GitHub%20Pages-blue)
![Matter.js](https://img.shields.io/badge/physics-Matter.js-amber)

一个基于 [Matter.js](https://brm.io/matter-js/) 的交互式二维物理模拟器，直接在浏览器中运行，无需安装。

🌐 **[在线体验](https://yshandrew.github.io/Physics-Lab/)**

---

## 功能

### 🧰 工具
- **选择**（`V`）— 点击选中物体，拖拽移动，查看/编辑属性
- **方块**（`B`）— 拖拽创建矩形刚体
- **圆球**（`C`）— 拖拽创建圆形刚体
- **斜面**（`R`）— 拖拽创建三角形斜面
- **平台**（`P`）— 拖拽创建静态平台
- **弹簧**（`S`）— 点击两个物体创建弹性约束
- **连杆**（`H`）— 点击两个物体创建刚性连接
- **绳链**（`K`）— 从起点拖到终点创建柔绳链
- **删除**（`D`）— 点击删除物体

### 🎯 交互
- **拖拽物体** — 选中模式下点击并拖拽移动任意物体
- **平移视角** — 按住空格 + 鼠标拖拽
- **缩放** — 滚轮缩放，或 `+/−` 键
- **属性面板** — 选中物体后实时编辑位置、速度、摩擦等参数
- **受力分析** — 显示重力、支持力、摩擦力、约束力、空气阻力的箭头
- **最小地图** — 左下角全局俯视图，显示视口范围

### ⚙️ 控制
| 快捷键 | 功能 |
|--------|------|
| `空格` | 暂停/继续模拟 |
| `V` | 选择工具 |
| `B` | 创建方块 |
| `C` | 创建圆球 |
| `R` | 创建斜面 |
| `P` | 创建平台 |
| `S` | 创建弹簧 |
| `H` | 创建连杆 |
| `K` | 创建绳链 |
| `D` | 删除模式 |
| `Delete` | 删除选中物体 |
| `0` | 重置视角 |
| `+/−` | 缩放 |
| `Esc` | 取消操作 |

---

## 项目结构

```
.
├── src/
│   └── index.html      ← 单文件应用（HTML + CSS + JS）
├── .github/
│   └── workflows/
│       └── deploy.yml  ← GitHub Pages 自动部署
├── package.json
└── README.md
```

所有代码在单个 `index.html` 中，无构建步骤。直接打开即可运行。

## 部署

本项目使用 GitHub Actions 自动部署到 GitHub Pages：

1. 推送 `main` 分支 → 触发 workflow
2. `src/` 目录内容被发布到 GitHub Pages
3. 访问 `https://<user>.github.io/<repo>/` 即可使用

## 技术栈

- **物理引擎**: [Matter.js](https://brm.io/matter-js/) v0.20.0
- **样式**: [Tailwind CSS](https://tailwindcss.com/)（CDN）
- **字体**: Inter + JetBrains Mono
- **部署**: GitHub Pages

## 本地运行

无需安装任何工具，直接用浏览器打开 `src/index.html` 即可。

如果需要本地开发服务器（热更新）：

```bash
npm run dev
# 或直接:
npx serve src
```

默认端口 3000，在浏览器打开 `http://localhost:3000` 即可预览。

## License

MIT
