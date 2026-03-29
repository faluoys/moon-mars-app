# moon-mars

`moon-mars` 是一个基于 `Vue 3 + TypeScript + Tauri 2 + Rust` 构建的跨平台桌面应用，面向音乐搜索、播放管理、主题定制与本地数据沉淀场景，目标是在轻量体积、原生能力与现代界面体验之间取得平衡。

项目采用 Web 前端负责交互与视图，Tauri 负责桌面容器与系统能力接入，Rust 负责底层能力扩展与原生性能支撑。整体定位不是简单的网页壳，而是一套可持续演进的桌面端音乐工作台。

## 项目亮点

- 多源音乐搜索与播放，覆盖常见在线音源场景。
- 支持播放队列、收藏、历史、歌单等完整的音乐数据管理能力。
- 提供主题切换、调色盘、自定义视觉风格等桌面级个性化配置。
- 基于 Tauri 2 接入文件导出、保存对话框、窗口控制、自动更新等原生能力。
- 提供播放配置、系统设置、更新检查等运维型界面，便于后续持续扩展。
- 兼顾桌面端体验与页面模块化组织，适合继续演进为完整的个人媒体工作台。

## 功能模块

### 音乐模块

- 音乐搜索、播放、切歌、歌词查看
- 当前播放队列管理
- 歌曲下载与歌词导出
- 分享弹窗与歌曲信息整理

### 音乐数据模块

- 播放历史
- 收藏列表
- 我的歌单与歌单明细管理
- 数据查询、导出、删除、清空等操作

### 设置模块

- 播放配置管理
- 系统行为配置
- 软件更新检查与安装
- 主题与视觉样式调整

### 扩展模块

- 首页信息展示
- 存储监控与磁盘信息
- 3D 相册等可视化内容模块

## 技术栈

| 层级 | 技术 |
| --- | --- |
| 前端框架 | Vue 3、Vue Router、TypeScript |
| UI 组件 | Naive UI、Vicons |
| 构建工具 | Vite、pnpm |
| 桌面容器 | Tauri 2 |
| 原生能力 | Rust、Tauri Plugins |
| 数据与图表 | IndexedDB、ECharts |

## 项目结构

```text
src/
  layout/           应用整体布局与壳层
  views/
    home/           首页
    music/          音乐播放模块
    shadowMoon/     历史、收藏、歌单数据模块
    settings/       播放配置、系统设置
    analytics/      可视化扩展模块
  router/           路由配置

src-tauri/
  src/              Rust 入口与原生命令
  capabilities/     Tauri 权限配置
  tauri.conf.json   桌面应用配置与 updater 配置
```

## 界面预览

以下截图链接默认面向公共仓库 `faluoys/moon-mars-app` 展示，公共仓库需同步保留 `demo` 目录中的图片资源。

### 首页

![首页](https://github.com/faluoys/moon-mars-tauri/blob/main/demo/index.png?raw=true)

### 音乐模块

![音乐模块](https://github.com/faluoys/moon-mars-tauri/blob/main/demo/music.png?raw=true)

### 主题配置

![主题配置](https://github.com/faluoys/moon-mars-tauri/blob/main/demo/CustomTheme.png?raw=true)

## 快速开始

### 环境要求

- Node.js 20+
- pnpm 10+
- Rust stable
- Tauri 2 开发环境

### 安装依赖

```bash
pnpm install
```

### 开发模式

```bash
pnpm tauri dev
```

### 类型检查

```bash
pnpm typecheck
```

### 前端构建

```bash
pnpm build
```

### 桌面端命令入口

```bash
pnpm tauri
```

## 自动更新

项目已接入 Tauri Updater，当前更新清单地址为：

```text
https://github.com/faluoys/moon-mars-app/releases/latest/download/latest.json
```

发布模式采用：

- 私有源码仓库负责构建
- 公共发布仓库负责 Release 与更新分发

## 数据与接口说明

音乐相关接口当前接入 `GD-Studio` 提供的音乐 API 服务，项目本身主要负责桌面端交互、数据组织与本地能力整合。

如果你准备将项目用于公开分发，建议进一步补充：

- 接口稳定性策略
- 错误回退与限流策略
- 法务与版权提示
- 隐私与数据存储说明

## 推荐开发工具

- VS Code
- Tauri VS Code Extension
- rust-analyzer

## 项目定位

`moon-mars` 不是单一的播放器页面，而是一套围绕音乐消费、数据沉淀、桌面体验和系统级能力整合构建的桌面应用基础框架。当前版本已经具备继续向以下方向扩展的基础：

- 更完整的媒体库管理
- 本地资源扫描与索引
- 多端配置同步
- 更成熟的更新与发布体系
- 面向个人工作流的音乐与内容管理能力
