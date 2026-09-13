# DSH 插件列表

> 记录当前 DSH 实例已安装的插件，用于在新环境按本清单快速恢复。
> 实例：`~/.dsh/profiles/web` ｜ DSH `0.1.5-rc.2` ｜ Node.js `v22.23.2` ｜ pnpm `11.26.0`
> 最后更新：2026-09-13（版本为快照记录，npm 最新版可能更高）

## 一、官方核心包（4）

| 包名 | 版本 | 说明 |
|------|------|------|
| [@deepseek-ai/dsh](https://www.npmjs.com/package/@deepseek-ai/dsh) | 0.1.5-rc.2 | DSH 核心引擎（CLI） |
| [@deepseek-ai/dsh-base](https://www.npmjs.com/package/@deepseek-ai/dsh-base) | 随核心包 | 基础 bundle：工具、会话、Web 搜索 / 抓取等 |
| [@deepseek-ai/dsh-web-app](https://www.npmjs.com/package/@deepseek-ai/dsh-web-app) | 随核心包 | Web 应用 bundle |
| [@deepseek-ai/dsh-headless](https://www.npmjs.com/package/@deepseek-ai/dsh-headless) | 随核心包 | 无头模式 bundle（headless profile） |

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

## 四、自建插件（1）

| 插件名称 | 版本 | 仓库 | 说明 |
|----------|------|------|------|
| web-search-scrape | 1.3.1 | [GitHub](https://github.com/BaihaWhite/dsh-web-search-scrape) | 自建：**可切换后端 + 计费硬保险**的网页检索。`local` = 六档分级（T1 极速 → T6 研究）抓取 DuckDuckGo / Bing / Baidu / Google / Yandex 与 7 个社交平台，**不调用任何付费 API**；`official` = 委托内置 DeepSeek 搜索（按 token 计费，默认被 `allowOfficial: false` 拦住）。另注册 `web_search_deep`（带 `tier`、上限 130 条，不被预设遮蔽）。v1.3.1 修复 DDG 解析的丢结果与重复项。MIT 许可 |

> **要求 DSH `>= 0.1.5-rc.2`**（见 `package.json` 的 `dsh.engines.dsh`）。v1.0.0 在该版本上会因设置 API 变更**直接加载失败**，必须 1.1.0+；计费保险与 `web_search_deep` 需 1.2.0+。

### 安装（零配置，无需手工改补丁）

仓库自带 `cordis.patch.yml` 并声明 `dsh.bundle.patch`，装完即自动挂载：

```sh
# 推荐：锁定 tag
dsh plugin --profile web add github:BaihaWhite/dsh-web-search-scrape#v1.3.1

# 或跟 main
dsh plugin --profile web add github:BaihaWhite/dsh-web-search-scrape

# 或 Release tarball（无需 git）
dsh plugin --profile web add \
  https://github.com/BaihaWhite/dsh-web-search-scrape/releases/download/v1.3.1/web-search-scrape-1.3.1.tgz
```

装完**重启 host**（`dsh web`）生效。仓库带 `dsh-plugin` topic，插件商店可检索到。

<details>
<summary>本地克隆 + 符号链接时才需要手工补丁</summary>

克隆目录**必须放在 profile 内**，否则裸导入解析不到宿主包：

```sh
cd ~/.dsh/profiles/web
git clone https://github.com/BaihaWhite/dsh-web-search-scrape.git web-search-scrape
ln -s ../web-search-scrape node_modules/web-search-scrape
```

再把仓库里 `cordis.patch.yml` 的内容（`web.searchProvider` 指向 `web-scrape`、停用 `tool-web` 的 search、插入插件行）复制进 profile 的 `cordis.patch.yml`。

⚠️ **别重复 insert**：loader 对重复行 id 会抛 `duplicate loader entry id`，host 将无法启动。
</details>

**计费**：默认配置下**零费用** —— `backend: local` 走抓取；`allowOfficial: false` 让官方后端即使被选中也拒绝且不发请求；`maxAutoTier: 3` 阻止「分析/对比/趋势」这类常见词自动升到会派发 LLM 子代理的 T4–T6。`web-search-deepseek` 行保持启用（官方后端的委托目标 + 官方「Web search」设置卡片）。

## 五、皮肤

| 皮肤 | 来源 | 状态 |
|------|------|------|
| blue-fantasy | `@linxin666/dsh-client-ui-skin-center` 内置 | 已启用（见 `~/.dsh/skin-center-active.json`） |
| miku / ths / trading | [创意工坊 dsh-market.com](https://dsh-market.com) | 未安装，按需从工坊获取 |

## 六、本次排除项（2）

| 插件 | 说明 |
|------|------|
| dsh-ocr | 按需排除，未安装 |
| attach-plus | 按需排除，未安装 |

## 七、与旧清单的名称对照

| 旧名称 | 现名称 / 替代 |
|--------|---------------|
| `@linxin666/dsh-web-ui-all` | `@linxin666/dsh-web-all`（聚合包重命名） |
| `@linxin666/dsh-client-ui-aionui-panel` | `dsh-better-sidebar`（右侧面板底座，功能更强） |
| `@linxin666/dsh-live-stats` | `@linxin666/dsh-usage`（使用统计） |
| `@linxin666/dsh-skins` | `@linxin666/dsh-client-ui-skin-center`（皮肤中心） |
| `web-search-scrape`（纯本地，无仓库） | 已有公开仓库 [BaihaWhite/dsh-web-search-scrape](https://github.com/BaihaWhite/dsh-web-search-scrape)，从「排除项」移入第四节，可自动恢复 |

## 八、安装命令

```sh
# 1) 社区插件全家桶（含 19 个子插件 + better-sidebar）
#    装本清单记录的版本：
dsh plugin --profile web add @linxin666/dsh-web-all@0.3.20
#    或装 npm 最新版：
# dsh plugin --profile web add @linxin666/dsh-web-all@latest

# 2) 插件商店
dsh plugin --profile web add dsh-plugin-store@0.1.0

# 3) 自建插件（公开仓库）
dsh plugin --profile web add github:BaihaWhite/dsh-web-search-scrape

# 4) 预检：确认没有 Cannot find package 报错
dsh --profile web --dump-config | grep -i "cannot find"

# 5) 重启 dsh web 生效（页面刷新不够）
```

## 九、安装排障要点（profile：`~/.dsh/profiles/web`）

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
