# 大仕国工 · KUKE 无人装备门户网站

纯静态 H5 企业官网，移动端适配，展示无人装备产品系列，中英双语、多主题。

## 在线访问

- **正式域名（HTTPS）**：`https://hanger-on.cc`（含 `www.hanger-on.cc`，Let's Encrypt 证书自动续期，HTTP 自动跳转 HTTPS）
- **镜像站（GitHub Pages）**：https://676020400yingchun.github.io/kuke-h5/
- **ICP 备案**：蜀ICP备2026058652号（页脚可点击跳转工信部备案系统）

## 技术栈

- 纯 HTML + CSS + JavaScript，无构建工具（单文件页面 + `assets/`）
- 响应式移动端设计（max-width 480px）
- 主题切换：科技蓝·白昼 / 科技蓝·暗夜 / 应急红·白昼 / 应急红·暗夜
- 中英文双语切换

## 功能模块

- **首页**：品牌展示、核心产品亮点、行动入口
- **装备**：全系装备目录，按分类筛选
  - 无人车系列（16 款）
  - 四足机器人系列
  - 无人机配套系列
  - 反制装备系列
  - 线控底盘系列
- **技术**：核心技术能力展示
- **我的**：企业介绍、理念、联系方式、访客统计

## 安全与体验

- **分享卡片**：Open Graph / Twitter 卡片（转发自动带站点缩略图，指向正式域名）
- **SEO**：robots.txt、canonical、favicon
- **安全**：Nginx 安全响应头 + CSP、URL hash 白名单（防选择器注入）、联系表单仅走编码后 `mailto:`
- **页面保护**：禁用复制/右键、OCR 干扰层
- **访客统计**：不蒜子（busuanzi，轮询健壮版，实时显示"您是第 N 位读者"）

## 本地开发

```bash
git clone https://github.com/676020400yingchun/kuke-h5.git
cd kuke-h5
python3 -m http.server 8765
```

浏览器打开 http://localhost:8765/

## 部署

### GitHub Pages（自动部署）

推送到 `main` 分支即自动部署：

```bash
git add .
git commit -m "update"
git push origin main
```

### 阿里云 ECS（正式线上）

- 服务器：阿里云 ECS `8.137.12.91`（成都 / 四川）
- 站点目录：`/var/www/kuke`（`index.html` + `assets/` + `favicon.ico` + `robots.txt`）
- Web：Nginx，配置 `/etc/nginx/conf.d/kuke.conf`
- HTTPS：Let's Encrypt 证书（`certbot --nginx`，自动续期），80 端口自动跳转 HTTPS
- 更新：`scp index.html root@8.137.12.91:/var/www/kuke/index.html` 后 `nginx -s reload`

> 域名 `hanger-on.cc` / `www` 已在 Cloudflare 解析（DNS only）指向该服务器。

## 联系方式

- 咨询热线：18030403818（王先生）
- 邮箱：1226273808@qq.com
- 地址：中国成都高新区梓州大道4111号易上创客中心
