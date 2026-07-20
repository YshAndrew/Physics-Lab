# Miaoda HTML App

Minimal single-file HTML app. dev/build 工具链由 [`@lark-apaas/coding-html-devserver`](https://www.npmjs.com/package/@lark-apaas/coding-html-devserver) 提供——vite 封装在内部，本项目不直接依赖 vite、也没有 `vite.config`。

## Structure

```
src/
  index.html      # 单文件：HTML + 内联 <style> + 内联 <script type="module">
package.json
```

## Scripts

```bash
npm install         # 安装工具链
npm run dev         # 启动 dev server（默认 8001），HMR 自动重载页面
npm run build       # 纯拷贝 src/ → dist/output/（不打包、不加 hash，产物 = 源码）
```

`dev` / `build` 背后是 `coding-html-devserver dev|build`。dev 借 vite 起 server 拿原生
HMR；build **不走 vite build**，纯拷贝 `src/` 到 `dist/output/`，保证产物逐字等于源码。

## 环境变量

| 变量 | 默认 | 说明 |
|---|---|---|
| `CLIENT_DEV_PORT` | `8001` | dev server 监听端口 |

dev server 不读 `CLIENT_BASE_PATH` 设 `base`：沙箱外部 URL 的 `/app/<appid>` prefix 由
平台网关独家负责，dev server 自己再设 `base` 会跟网关叠加，导致需要
`/app/<id>/app/<id>/` 两层才能访问。

## Dev server endpoints

- `/` → `src/index.html`（HMR 已启用）
- `/dev/health` → `{ "ready": true }`（探活接口；server 真正 listening 后才返回 `ready: true`）

沙箱网关接入时外部访问 `https://<host>/app/<appid>/`，网关把 `/app/<appid>` prefix
剥掉转给 dev server，dev server 这边只看到根路径。
