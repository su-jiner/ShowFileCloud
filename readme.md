<div align="center">

<img src="docs/public/screenshots/retrieve.webp" alt="ShowFileCloud" width="860" />

<p><em>匿名口令分享文本和文件，像取快递一样取文件</em></p>

[![GitHub stars](https://img.shields.io/github/stars/su-jiner/ShowFileCloud)](https://github.com/su-jiner/ShowFileCloud/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/su-jiner/ShowFileCloud)](https://github.com/su-jiner/ShowFileCloud/network)
[![GitHub issues](https://img.shields.io/github/issues/su-jiner/ShowFileCloud)](https://github.com/su-jiner/ShowFileCloud/issues)
[![GitHub license](https://img.shields.io/github/license/su-jiner/ShowFileCloud)](https://github.com/su-jiner/ShowFileCloud/blob/master/LICENSE)

</div>

## 简介

ShowFileCloud 是一个基于 FastAPI + Vue3 开发的轻量级文件分享工具。用户通过简单的方式分享文本和文件，
接收者只需要一个提取码就能取得文件，就像从快递柜取出快递一样简单。

- 🚀 快速部署：支持 Docker 一键部署
- 🔒 安全可靠：文件访问需要提取码
- ⏱️ 时效控制：支持按时间或取件次数失效
- 🗂️ 多种存储：本地、S3、OneDrive、WebDAV 与 OpenDAL
- 📱 响应式设计：适配移动端与桌面端

## 快速开始

### Docker 部署（推荐）

```bash
docker run -d --restart unless-stopped \
  -p 12345:12345 \
  -v sfc-data:/app/data \
  -e APP_ENV=production \
  -e LOG_LEVEL=warning \
  --log-opt max-size=10m \
  --log-opt max-file=3 \
  --name showfilecloud \
  su-jiner/showfilecloud:2.7.1 # x-release-please-version
```

打开 `http://localhost:12345`，按引导完成首次初始化。

### Docker Compose

```bash
docker compose up -d
```

### 手动部署

```bash
git clone https://github.com/su-jiner/ShowFileCloud.git
cd ShowFileCloud
pip install -r requirements.txt
python main.py
```

## 文档

完整的使用、配置与 API 文档位于 [`docs/`](docs/index.md)，或访问在线文档站点。

## 项目结构

```
ShowFileCloud/
├── apps/           # 应用代码
│   ├── admin/      # 管理后台
│   └── base/       # 基础功能
├── core/           # 核心功能
├── data/           # 数据目录
├── docs/           # VitePress 文档
└── sfc-fronted/    # 前端代码（构建镜像时从 GitHub 拉取）
```

## 贡献指南

1. Fork 本项目
2. 创建新分支 `git checkout -b feature/xxx`
3. 提交更改 `git commit -m 'Add xxx'`
4. 推送到分支 `git push origin feature/xxx`
5. 提交 Pull Request

## 免责声明

本项目开源仅供学习使用，不得用于任何违法用途，否则后果自负，与作者无关。使用时请保留项目地址和版权信息。