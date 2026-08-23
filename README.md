# DSH 插件列表

这是一个用于记录和管理 DeepSeek Harness (DSH) 已安装插件的仓库。

## 📋 仓库内容

- **README.md** - 本文件，包含仓库介绍和安装提示词
- **list.md** - 完整的插件列表，包含所有插件的项目网址

## 🔍 已安装插件概览

当前 DSH 实例已安装以下插件：

### 核心包 (4个)
- @deepseek-ai/dsh
- @deepseek-ai/dsh-base
- @deepseek-ai/dsh-web-app
- @deepseek-ai/dsh-headless

### 社区插件 (10个)
来自 @linxin666/dsh-web-ui-all 全家桶：
- 任务看板 (task-board)
- 右侧面板 (aionui-panel)
- Git 图形化 (git-graph)
- Web UI 设置 (web-ui-settings)
- 宠物挂件 (pet)
- SSH 远程运维 (ssh)
- 实时统计 (live-stats)
- 远程 Web UI (remote-web-ui)
- 皮肤系统 (skins)
- 兼容层 (web-ui-all)

### 插件商店 (1个)
- dsh-plugin-store

### 自定义插件 (3个)
- dsh-ocr (OCR 视觉识别)
- attach-plus (文件上传增强)
- web-search-scrape (网页搜索)

**总计: 18个插件**

## 🚀 安装提示词

将以下提示词发送给 AI 助手，即可自动安装 list.md 中的所有插件：

---

**提示词：**

```
请安装 list.md 中的插件，并使用每个插件的仓库所要求的安装方式或通用规范方式来安装。如果有插件商店插件可以尝试通过插件商店安装，确保插件和 list.md 的完全匹配即可。

具体步骤：
1. 首先读取 list.md 文件获取完整插件列表
2. 对于每个插件，访问其仓库地址查看安装说明
3. 按照仓库要求的方式安装插件：
   - 如果仓库有 README 安装说明，按照说明操作
   - 如果是 npm 包，使用 npm install 或 pnpm add 安装
   - 如果是插件商店插件，通过 dsh-plugin-store 安装
4. 安装完成后，更新 DSH 配置文件（如 cordis.patch.yml）
5. 重启 DSH Web 服务使插件生效

注意事项：
- 保持插件版本与 list.md 中记录的一致
- 自定义插件需要手动配置路径
- 安装前备份现有配置
```

---

## 📝 使用说明

### 查看插件列表
```bash
# 查看所有插件
cat list.md

# 或使用 GitHub 查看
# https://github.com/BaihaWhite/dsh-plugins-list/blob/main/list.md
```

### 安装新插件
1. 编辑 `list.md` 添加新插件信息
2. 使用上述提示词让 AI 助手安装
3. 或手动按照插件仓库说明安装

### 更新插件
1. 检查各插件仓库的最新版本
2. 更新 `list.md` 中的版本信息
3. 使用包管理器更新插件

## 🔗 相关链接

- [DSH 官方仓库](https://github.com/deepseek-ai/dsh)
- [dsh-web-ui 全家桶](https://github.com/zhu1090093659/dsh-web-ui)
- [dsh-plugin-store](https://github.com/w769721503/dsh-plugin-store)

## 📄 许可证

本仓库遵循 MIT 许可证。各插件的许可证请参考各自的原始仓库。