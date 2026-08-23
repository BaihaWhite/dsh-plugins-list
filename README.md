# DSH 插件列表

本仓库记录当前 DSH (DeepSeek Harness) 实例中已安装的所有插件，包括官方插件、社区插件和自定义插件。

## 📦 已安装插件概览

### 核心插件包

| 包名 | 版本 | 说明 |
|------|------|------|
| `@deepseek-ai/dsh` | 0.1.0-rc.6 | DSH 核心引擎 |
| `@deepseek-ai/dsh-base` | - | DSH 基础包 |
| `@deepseek-ai/dsh-web-app` | - | DSH Web 应用 |
| `@deepseek-ai/dsh-headless` | - | DSH 无头模式 |

### Web UI 插件 (来自 @linxin666/dsh-web-ui-all v0.1.10)

| 插件 ID | 包名 | 功能 |
|---------|------|------|
| `ui-web-ui-compat` | `@linxin666/dsh-web-ui-all` | Web UI 兼容层 |
| `ui-web-ui-settings` | `@linxin666/dsh-client-ui-web-ui-settings` | Web UI 设置页面 |
| `ui-dsh-aionui-panel` | `@linxin666/dsh-client-ui-aionui-panel` | 右侧面板系统（文件树、预览、SCM 变更） |
| `ui-task-board` | `@linxin666/dsh-client-ui-task-board` | 任务看板（支持 cron 定时任务） |
| `ui-git-graph` | `@linxin666/dsh-client-ui-git-graph` | Git 图形化界面 |
| `pet` | `@linxin666/dsh-pet` | 宠物挂件 |
| `remote-web-ui` | `@linxin666/dsh-remote-web-ui` | 远程 Web UI |
| `live-stats` | `@linxin666/dsh-live-stats` | 实时统计 |
| `ssh` | `@linxin666/dsh-ssh` | SSH 远程运维 |
| `ui-skin-center` | `@linxin666/dsh-client-ui-skin-center` | 皮肤中心 |

### 皮肤插件 (来自 @linxin666/dsh-skins v0.1.10)

| 皮肤 ID | 包名 | 说明 |
|---------|------|------|
| `dsh-client-ui-skin-blue-fantasy` | `@linxin666/dsh-skins/skins/blue-fantasy` | 蓝色幻想主题 |
| `dsh-client-ui-skin-miku` | `@linxin666/dsh-skins/skins/miku` | 初音未来主题 |
| `dsh-client-ui-skin-ths` | `@linxin666/dsh-skins/skins/ths` | 同花顺主题 |
| `dsh-client-ui-skin-trading` | `@linxin666/dsh-skins/skins/trading` | 交易主题 |

### 插件商店

| 包名 | 版本 | 说明 |
|------|------|------|
| `dsh-plugin-store` | 0.1.0 | DSH 插件商店（GitHub: w769721503/dsh-plugin-store） |

### 自定义插件

| 插件 ID | 包名 | 功能 | 来源 |
|---------|------|------|------|
| `dsh-ocr` | `dsh-ocr` | OCR 视觉识别插件 | `<local>/projects/mcp-ds-ocr` |
| `attach-plus` | `attach-plus` | 输入框 "+" 上传按钮 | `<local>/projects/dsh-local-upload` |
| `web-search-scrape` | `web-search-scrape` | 自定义网页搜索（DuckDuckGo/Bing/Baidu/Google） | 本地配置 |

## 📁 仓库结构

```
dsh-plugins-list/
├── README.md                    # 本文件
├── plugins.json                 # 插件列表 JSON 格式
├── installed-packages.md        # 已安装 npm 包详情
├── profiles/
│   ├── web/                     # Web profile 配置
│   │   ├── package.json
│   │   └── cordis.patch.yml
│   └── headless/                # Headless profile 配置
│       └── package.json
└── configurations/
    ├── settings.yaml            # DSH 设置文件
    └── cordis.patch.yml         # 主 cordis 补丁配置
```

## 🔧 配置说明

### Web Profile 插件配置

Web profile 的插件通过 `@linxin666/dsh-web-ui-all` 聚合包安装，包含以下功能模块：

- **任务看板** (`ui-task-board`): 多列看板管理任务，支持 5 段 cron 定时执行
- **右侧面板** (`ui-dsh-aionui-panel`): Explorer 文件树、Preview 多 tab 预览、SCM 变更面板
- **SSH 远程运维** (`ssh`): 主机配置、持久连接池、Web 终端
- **宠物挂件** (`pet`): 可爱的桌面宠物
- **Git 图形化** (`ui-git-graph`): 可视化 Git 历史
- **皮肤系统** (`dsh-skins`): 多种主题皮肤

### 自定义插件配置

自定义插件通过 `cordis.patch.yml` 注入到 Web profile：

```yaml
# 网页搜索插件
- insert:
    - id: web-search-scrape
      name: 'web-search-scrape'
      config:
        engines: [duckduckgo, bing, baidu, google, yandex]
        socials: [weixin, bilibili, weibo, x, zhihu, douyin, reddit]

# OCR 视觉识别插件
- insert:
    - id: dsh-ocr
      name: 'dsh-ocr'
      config: {}

# 文件上传插件
- insert:
    - id: attach-plus
      name: 'attach-plus'
      config: {}
```

## 📊 插件统计

- **官方核心包**: 4 个
- **Web UI 插件**: 10 个（来自 @linxin666/dsh-web-ui-all）
- **皮肤插件**: 4 个
- **插件商店**: 1 个
- **自定义插件**: 3 个
- **总计**: 22 个插件

## 🚀 安装新插件

### 通过插件商店

1. 打开 DSH Web GUI
2. 进入「设置 → 插件」
3. 使用 `dsh-plugin-store` 浏览和安装插件

### 手动安装

1. 将插件包放入 `~/.dsh/profiles/web/node_modules/` 目录
2. 在 `cordis.patch.yml` 中添加插件配置
3. 重启 DSH Web 服务

## 📝 更新日志

- **2026-08-23**: 创建插件列表仓库，记录当前已安装的 22 个插件
- **2026-08-16**: 安装自定义插件（dsh-ocr, attach-plus, web-search-scrape）
- **2026-08-15**: 安装 @linxin666/dsh-web-ui-all 全家桶插件

## 🔗 相关链接

- [DSH 官方仓库](https://github.com/deepseek-ai/dsh)
- [dsh-web-ui 全家桶](https://github.com/zhu1090093659/dsh-web-ui)
- [dsh-plugin-store](https://github.com/w769721503/dsh-plugin-store)
- [DSH 文档](https://dsh.deepseek.com)

## 📄 许可证

本仓库中的文档和配置文件遵循 MIT 许可证。各插件的许可证请参考各自的原始仓库。