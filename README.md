# DSH 插件列表

这是一个用于记录和管理 DeepSeek Harness (DSH) 已安装插件的仓库。

## 📋 仓库内容

- **README.md** - 本文件，包含仓库介绍和安装提示词
- **list.md** - 完整的插件列表，包含所有插件的项目网址与版本

## 🔍 已安装插件概览

当前 DSH 实例（`~/.dsh/profiles/web`，DSH `0.1.5-rc.2`）已安装 **26 个包**：

### 核心包 (4个)
- @deepseek-ai/dsh
- @deepseek-ai/dsh-base
- @deepseek-ai/dsh-web-app
- @deepseek-ai/dsh-headless

### 社区插件全家桶 (1 聚合包 → 19 子插件 + 1 外部插件)
来自 `@linxin666/dsh-web-all@0.3.20`：
- 任务看板 (task-board)
- Git 图形化 (git-graph)
- Web UI 设置 (web-ui-settings)
- 宠物挂件 (pet)
- SSH 远程运维 (ssh)
- 远程 Web UI (remote-web-ui)
- 使用统计 (usage)
- 会话归档 (session-archive)
- 模型能力 (model-capabilities)
- 皮肤中心 (skin-center)
- 预设中心 (preset-center)
- 技能浏览器 (skill-explorer)
- 插件管理器 (plugin-manager)
- 社区插件 (community-plugins)
- 创意工坊 (market)
- 图片描述 (describe-image)
- 环境诊断 (doctor)
- 国际化 (i18n)
- 量神 (liangshen)
- 右侧面板 (dsh-better-sidebar，外部集成)

### 插件商店 (1个)
- dsh-plugin-store

### 自建插件 (1个)
- web-search-scrape（六档分级抓取式网页检索，[BaihaWhite/dsh-web-search-scrape](https://github.com/BaihaWhite/dsh-web-search-scrape)）

### 本次排除项 (2个)
- dsh-ocr
- attach-plus

> 旧清单中的 `aionui-panel`、`live-stats`、`dsh-skins` 已被新全家桶取代
> （分别对应 `dsh-better-sidebar`、`dsh-usage`、`skin-center`），详见 list.md 的名称对照表。

## 🚀 安装提示词

将以下提示词发送给 AI 助手，即可按 list.md 记录的版本恢复全部插件：

---

**提示词：**

```
请按 list.md 恢复本机 DSH 插件，使用 list.md 记录的安装方式。

具体步骤：
1. 读取 list.md 获取完整插件清单与「本次排除项」
2. 确认目标 profile 为 ~/.dsh/profiles/web，并按 list.md「安装排障要点」调整 pnpm-workspace.yaml
   （nodeLinker: hoisted、minimumReleaseAgeExclude: '@linxin666/*'、allowBuilds: cloudflared/cpu-features/node-pty/ssh2）
3. 依次执行安装命令（等号后为 list.md 记录的版本，装最新版则把 @0.3.20 换成 @latest）：
   - dsh plugin --profile web add @linxin666/dsh-web-all@0.3.20
   - dsh plugin --profile web add dsh-plugin-store@0.1.0
   - dsh plugin --profile web add github:BaihaWhite/dsh-web-search-scrape
     （自建插件，公开仓库；装好后还需按该仓库 README
      配置 cordis.patch.yml——把 web.searchProvider 指向 web-scrape、停用内置
      tool-web 的 search、并把插件加入 insert 段）
4. 预检：dsh --profile web --dump-config，确认没有 "Cannot find package" 报错
5. 重启 dsh web 使插件生效

注意事项：
- 排除 list.md「本次排除项」中的 dsh-ocr 与 attach-plus，不要安装
- web-search-scrape 已从「排除项」移入 list.md 第四节「自建插件」，现在可自动恢复；
  该仓库为公开仓库，无需 GitHub 凭据即可 clone
- 不要重复安装旧名包（aionui-panel / live-stats / dsh-skins / dsh-web-ui-all），已被新全家桶取代，重复装会因 id 冲突挂载失败
- 安装前备份 package.json、cordis.patch.yml、pnpm-workspace.yaml
- 皮肤 blue-fantasy 随 skin-center 内置，miku / ths / trading 需从创意工坊按需安装
- 本清单是**版本快照**：npm 上的最新版可能已高于此记录的版本
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
3. 重启 `dsh web` 后可在「设置 → 插件」中一键更新

## 🔗 相关链接

- [DSH 官方包（npm）](https://www.npmjs.com/package/@deepseek-ai/dsh)
- [dsh-web 全家桶](https://github.com/zhu1090093659/dsh-web)
- [dsh-plugin-store 插件商店](https://github.com/yunhuantian/dsh-plugin-hub)
- [dsh-better-sidebar 右侧面板](https://github.com/omdsh-dev/DSH-better-sidebar)
- [dsh-web-search-scrape 自建检索插件](https://github.com/BaihaWhite/dsh-web-search-scrape)
- [创意工坊 dsh-market.com](https://dsh-market.com)

## 📄 许可证

本仓库遵循 MIT 许可证。各插件的许可证请参考各自的原始仓库。
