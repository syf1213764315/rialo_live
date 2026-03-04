# Rialo Live (静态站)

这是一个小型静态页面，用于展示 Web3 直播界面并能播放 HLS 直播流。已经包含配置以直接部署到 Vercel（`vercel.json`）。

快速开始（本地预览）

1. 确保在项目根目录：

```powershell
cd d:\source\node\web\rialo
```

2. 使用 `serve` 快速启动本地静态服务器（如果没有 `serve`，命令会用 npx 下载并执行）：

```powershell
npm run start
# 然后打开 http://localhost:3000
```

在 Vercel 上部署

- 将此仓库推到 GitHub，然后在 Vercel 中导入仓库，使用默认设置即可部署为静态站点。
- `vercel.json` 已包含基础静态构建配置。

替换为真实直播流

- 默认使用了一个公开 HLS 测试流：`https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8`。
- 若要接入你的真实直播 m3u8 地址，请打开 `index.html` 并找到顶部脚本中 `STREAM_URL` 常量，将其替换为你的 m3u8 地址。

注意事项

- HLS 在 Safari/iOS 上原生支持；在大多数桌面浏览器（Chrome/Firefox）上使用 hls.js 转码并播放。
- 若需要把直播地址作为可配置项（不想直接写在 HTML），可以考虑把地址放到一个简单的 JSON 配置文件并在部署时替换，或通过后端 API 提供（需要服务器端支持）。

如需我把真实 m3u8 地址写入并帮你做其他部署自动化（如 CI/CD、环境变量注入等），把地址或需求告诉我即可。