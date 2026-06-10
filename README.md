# Cortex 官网 · cortex-website

[Cortex 智枢](https://github.com/yourname/cortex) 的产品落地页 — 单页 HTML，无构建步骤，直接由 GitHub Pages 托管。

## 本地预览

```bash
# 任意静态服务器都行，举例：
python3 -m http.server 8000
# 然后打开 http://127.0.0.1:8000
```

或者直接双击 `index.html`，浏览器里也能跑（Tailwind 走 CDN）。

## 部署到 GitHub Pages（5 分钟）

### 1. 在 GitHub 建公开仓

打开 https://github.com/new

- Repository name: `cortex-website`（或随意）
- **Public**
- 不要勾 README（这边已经写好了）

### 2. 推送代码

```bash
cd /Users/mac/Documents/knowledge/trade/cortex-website
git init
git add .
git commit -m "init: Cortex landing page"
git branch -M main
git remote add origin git@github.com:yourname/cortex-website.git
git push -u origin main
```

### 3. 开启 Pages

在仓库页面：

1. **Settings** → 左侧 **Pages**
2. **Source** → 选 `Deploy from a branch`
3. **Branch** → `main` / `/ (root)` → Save
4. 等 1~2 分钟，回到 Pages 页面看到 ✅ `Your site is live at https://yourname.github.io/cortex-website/`

## 绑自定义域名（可选）

如果你有域名（比如 `cortex.fenxianglife.com`）：

1. 在域名 DNS 控制台加一条 **CNAME** 记录：
   - 主机记录：`cortex`（或 `@`）
   - 记录值：`yourname.github.io`
2. 仓库根目录加一个 `CNAME` 文件，内容就是 `cortex.fenxianglife.com`
3. Settings → Pages → Custom domain 里填这个域名 → Save
4. 等 DNS 生效（10 分钟 ~ 几小时），GitHub 自动给你签 HTTPS 证书

## 待办

在正式发布前需要修改 `index.html`：

- [ ] 第 ~245 行 `[ 微信二维码占位 ]` — 换成你的真实微信二维码（建议 `assets/wechat-qr.png` 再 `<img src="...">`）
- [ ] 第 ~330 行 `urls` — 替换成实际的 DMG 下载链接（阿里云 OSS / Cloudflare R2 / 其他 CDN）
- [ ] 顶部 nav 的 Cortex logo 字号 / 主标语，看心情可改
- [ ] FAQ 末尾"开源吗"一条根据实际策略调整

## 文件结构

```
cortex-website/
├── index.html      # 全部页面（单文件）
├── README.md       # 本文档
└── CNAME           # （可选）自定义域名
```

后续如果加截图：
```
assets/
├── screenshots/
│   ├── dashboard.png
│   └── strategy-detail.png
└── wechat-qr.png
```
