# DSH 插件列表

> 记录当前 DSH 实例已安装的插件，用于在新环境按本清单快速恢复。
> 实例：`~/.dsh/profiles/web` ｜ DSH `0.1.5-rc.2` ｜ Node.js `v22.23.2` ｜ pnpm `11.26.0`
> 最后更新：2026-09-11

## 一、官方核心包（4）

| 包名 | 版本 | 说明 |
|------|------|------|
| [@deepseek-ai/dsh](https://github.com/deepseek-ai/dsh) | 0.1.5-rc.2 | DSH 核心引擎（CLI） |
| [@deepseek-ai/dsh-base](https://github.com/deepseek-ai/dsh) | 随核心包 | 基础 bundle：工具、会话、Web 搜索 / 抓取等 |
| [@deepseek-ai/dsh-web-app](https://github.com/deepseek-ai/dsh) | 随核心包 | Web 应用 bundle |
| [@deepseek-ai/dsh-headless](https://github.com/deepseek-ai/dsh) | 随核心包 | 无头模式 bundle（headless profile） |

## 二、社区插件全家桶（1 聚合包 + 19 子插件 + 1 外部插件）

聚合包：**[`@linxin666/dsh-web-all@0.3.20`](https://github.com/zhu1090093659/dsh-web)**
安装这一个包即挂载下表全部子插件（子包均声明为其依赖）。

| 子包 | 版本 | 功能 |
|------|------|------|
| `@linxin666/dsh-client-ui-task-board` | 0.3.20 | 任务看板：多列看板 + cron 定时真实执行 |
| `@linxin666/dsh-client-ui-git-graph` | 0.3.20 | Git 图形化：分支选择器 + 提交历史图谱 |
| `@linxin666/dsh-client-ui-web-ui-settings` | 0.3.20 | Web UI 设置页面 |
| `@linxin666/dsh-pet` | 0.3.20 | 宠物挂件 |
| `@linxin666/dsh-ssh` | 0.3.20 | SSH 远程运维：终端 / 传输 / 隧道 / 集群 |
| `@linxin666/dsh-remote-web-ui` | 0.3.20 | 远程 Web UI：手机 / PC 浏览器扫码配对 |
| `@linxin666/dsh-usage` | 0.3.20 | 使用统计：token 用量、供应商余额、套餐额度 |
| `@linxin666/dsh-session-archive` | 0.3.20 | 会话归档管理：批量归档 / 恢复 / 删除 |
| `@linxin666/dsh-client-ui-model-capabilities` | 0.3.20 | 模型能力：逐模型声明图片输入与推理档位 |
| `@linxin666/dsh-client-ui-skin-center` | 0.3.20 | 皮肤中心：内置 blue-fantasy |
| `@linxin666/dsh-client-ui-preset-center` | 0.3.20 | Agent 预设中心 |
| `@linxin666/dsh-client-ui-skill-explorer` | 0.3.20 | 技能浏览器 |
| `@linxin666/dsh-client-ui-plugin-manager` | 0.3.20 | 插件管理器 |
| `@linxin666/dsh-client-ui-community-plugins` | 0.3.20 | 社区插件入口 |
| `@linxin666/dsh-client-ui-market` | 0.3.20 | 创意工坊（dsh-market.com） |
| `@linxin666/dsh-tool-describe-image` | 0.3.20 | 图片描述工具 |
| `@linxin666/dsh-doctor` | 0.3.20 | 环境诊断 |
| `@linxin666/dsh-i18n` | 0.3.20 | 界面国际化 |
| `@linxin666/dsh-liangshen` | 0.3.20 | 量神 |
| [dsh-better-sidebar](https://github.com/omdsh-dev/DSH-better-sidebar) | 0.19.0-alpha.1 | 右侧面板（外部集成插件）：文件渲染编辑 / 编辑器 / 终端 / 侧边对话 / Git / 子代理 |

## 三、插件商店（1）

| 插件名称 | 版本 | 仓库 | 说明 |
|----------|------|------|------|
| dsh-plugin-store | 0.1.0 | [GitHub](https://github.com/yunhuantian/dsh-plugin-hub) | 插件商店：浏览 / 搜索 / 一键安装 / 更新 / 卸载 |

## 四、皮肤

| 皮肤 | 来源 | 状态 |
|------|------|------|
| blue-fantasy | `@linxin666/dsh-client-ui-skin-center` 内置 | 已启用（见 `~/.dsh/skin-center-active.json`） |
| miku / ths / trading | [创意工坊 dsh-market.com](https://dsh-market.com) | 未安装，按需从工坊获取 |

## 五、本次排除项

| 插件 | 说明 |
|------|------|
| dsh-ocr | 按需排除，未安装 |
| attach-plus | 按需排除，未安装 |
| web-search-scrape | 纯本地自定义插件，无仓库、无 npm 包，未纳入自动恢复 |

## 六、与旧清单的名称对照

| 旧名称 | 现名称 / 替代 |
|--------|---------------|
| `@linxin666/dsh-web-ui-all` | `@linxin666/dsh-web-all`（聚合包重命名） |
| `@linxin666/dsh-client-ui-aionui-panel` | `dsh-better-sidebar`（右侧面板底座，功能更强） |
| `@linxin666/dsh-live-stats` | `@linxin666/dsh-usage`（使用统计） |
| `@linxin666/dsh-skins` | `@linxin666/dsh-client-ui-skin-center`（皮肤中心） |

## 七、安装命令

```sh
# 1) 社区插件全家桶（含 19 个子插件 + better-sidebar）
dsh plugin --profile web add @linxin666/dsh-web-all@latest

# 2) 插件商店
dsh plugin --profile web add dsh-plugin-store@latest

# 3) 预检：确认没有 Cannot find package 报错
dsh --profile web --dump-config | grep -i "cannot find"

# 4) 重启 dsh web 生效（页面刷新不够）
```

## 八、安装排障要点（profile：`~/.dsh/profiles/web`）

`pnpm-workspace.yaml` 应包含：

```yaml
packages:
  - .

nodeLinker: hoisted
autoInstallPeers: false
minimumReleaseAgeExclude:
  - '@linxin666/*'
allowBuilds:
  cloudflared: true
  cpu-features: true
  node-pty: true
  ssh2: true
```

- **`nodeLinker: hoisted`**：pnpm 严格布局只把聚合包放顶层，子包会被收进嵌套目录，`dsh web` 会报 `Cannot find package '@linxin666/dsh-...'`。
- **`minimumReleaseAgeExclude`**：绕过 pnpm 11 的发布年龄门禁，否则新版本发布 24 小时内会静默装回旧版（旧版皮肤插件会导致 `dsh web` 启动崩溃）。
- **`allowBuilds`**：放行 `cloudflared` / `cpu-features` / `node-pty` / `ssh2` 的构建脚本，否则报 `ERR_PNPM_IGNORED_BUILDS`，SSH 终端与隧道功能不可用。
