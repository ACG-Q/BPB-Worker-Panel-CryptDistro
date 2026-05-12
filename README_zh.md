# BPB-Worker-Panel-CryptDistro

<img src="logo_zh.svg" alt="BPB-Worker-Panel-CryptDistro" width="500" />

**[English](README.md)** | 中文版

### 通过加密和混淆实现安全代码分发

## 功能特性

- **高级加密**：利用最先进的加密技术保护您的代码免受未授权访问和篡改。
- **混淆能力**：保护您的代码免受逆向工程的侵害，使恶意行为者难以理解或修改您的代码。
- **自动化工作流**：每日检查上游更新，自动构建、混淆并发布新版本。
- **适配 Cloudflare Workers**：输出针对 Cloudflare Pages 部署进行了优化。

## 推荐部署方式

1. 从 GitHub Releases 下载 Release 包。
2. 在 Cloudflare Pages 中创建新项目。
3. 上传分发的 zip 文件（`_worker.zip`）。
4. 完成部署。

> 详细信息请参考：[Installation (Pages - New recommended method)](https://github.com/bia-pain-bache/BPB-Worker-Panel/blob/main/docs/pages_upload_installation_fa.md)

## 配置说明

### 环境变量

工作流使用以下可自定义的环境变量：

| 变量 | 默认值 | 说明 |
|------|--------|------|
| `TARGET_REPO` | `bia-pain-bache/BPB-Worker-Panel` | 获取源码的上游仓库 |
| `ENTRY_DIR` | `src` | 入口文件所在目录 |
| `ENTRY_NAME` | `worker` | 入口文件名（不含扩展名） |

### 工作流

- **`build.yml`**：每日定时构建，检查上游版本更新并在有新版本时创建发布。
- **`build-night.yml`**：基于最新 commit 的夜间构建，创建预发布版本。

## 混淆选项

混淆器配置（`obfuscator.json`）包括：

- 高级混淆预设
- 字符串数组编码（RC4 + Base64）
- 混淆标识符名称
- 死代码注入（50% 阈值）
- Unicode 转义序列

## 许可证

本项目仅供安全代码分发目的使用。
