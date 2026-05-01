# GPT Image2 Console

我的 GitHub Pages：

https://driannauer.github.io/gpt_image2_console/

原作者仓库：

https://github.com/CookSleep/gpt_image_playground

GPT Image2 Console 是一个基于 OpenAI 兼容图像接口的图片生成与编辑工具，保留本地历史记录、参考图、遮罩编辑、多配置切换、API 代理与批量管理等功能。

## 功能

- 支持 Images API、Responses API 与 fal.ai 图像接口。
- 支持参考图上传、拖拽排序、遮罩绘制与图片编辑。
- 支持本地 IndexedDB 历史记录、收藏、筛选、批量选择、导入与导出。
- 支持 Docker API 代理、本地开发代理与 URL 参数快速填充。
- 页面内已移除原仓库链接和版本更新提示，页面标题使用 GPT Image2 Console。

## 本地开发

```bash
npm install
npm run dev
```

如果本地接口存在 CORS 限制，可以复制 `dev-proxy.config.example.json` 为 `dev-proxy.config.json` 后配置代理目标。

## 构建

```bash
npm run build
```

构建产物会输出到 `dist/`，推送到 `main` 后 GitHub Actions 会重新发布 GitHub Pages。

## Docker

容器运行时可通过环境变量设置默认 API 和代理：

- `DEFAULT_API_URL`：页面默认显示的 API 地址。
- `API_PROXY_URL`：容器内代理转发目标地址。
- `ENABLE_API_PROXY`：设为 `true` 开启同源 API 代理。
- `HOST` / `PORT`：指定容器内 Nginx 监听地址与端口。

旧版 `API_URL` 会作为 `DEFAULT_API_URL` 与 `API_PROXY_URL` 的兜底值继续兼容。

## License

MIT
