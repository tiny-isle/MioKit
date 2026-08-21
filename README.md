# MioKit

<p align="center">
  <strong>Windows 上的键盘优先效率工作台</strong>
</p>

<p align="center">
  用一个全局搜索框启动应用、查找文件、执行系统操作，并通过插件扩展你的工作流。
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9n64fzj6nsk3">下载安装</a> ·
  <a href="https://www.tinyisle.cn/">官方网站</a> ·
  <a href="https://www.tinyisle.cn/plugins">浏览插件</a> ·
  <a href="docs/user-guide.md">用户指南</a> ·
  <a href="docs/developer/README.md">开发者文档</a>
</p>

<p align="center">
  <a href="https://apps.microsoft.com/detail/9n64fzj6nsk3">
    <img src="https://get.microsoft.com/images/en-us%20dark.svg" width="200" alt="从 Microsoft Store 获取 MioKit">
  </a>
</p>

![MioKit 搜索框首页](assets/images/search-index.png)

## 为什么使用 MioKit？

MioKit 把常用的 Windows 操作集中到一个快速、可扩展的搜索入口中。按下 `Alt + Space`，输入几个字即可：

| 能力 | 说明 |
| --- | --- |
| 快速启动 | 启动桌面应用、Microsoft Store 应用和自定义启动项 |
| 文件与系统搜索 | 搜索文件、文件夹、Windows 设置并执行系统操作 |
| 高效输入 | 支持拼音、缩写和中英文混合搜索 |
| 上下文操作 | 结合当前窗口、剪贴板和资源管理器环境提供相关操作 |
| 插件扩展 | 添加新的搜索结果、操作节点、Command 和自定义界面 |

数据默认保存在本机，插件和功能可以按需启用。

## 快速开始

1. 从 [Microsoft Store](https://apps.microsoft.com/detail/9n64fzj6nsk3) 安装 MioKit。
2. 完成首次启动设置后，按下 `Alt + Space` 呼出搜索框。
3. 输入应用、文件、设置或功能名称，按 `Enter` 执行。

更多安装、首次启动和插件使用说明，请阅读[用户指南](docs/user-guide.md)。

## 功能一览

### 搜索结果与快捷操作

输入关键词即可查看匹配结果，并通过结果菜单打开所在目录、复制路径、管理固定状态、设置全局快捷键、设置别名或执行插件提供的操作。

![MioKit 搜索结果](assets/images/search-result.png)

### 插件扩展

插件可以把剪贴板、表达式计算、待办清单、网页快开、Everything 搜索等工具接入 MioKit 的统一搜索框，也可以提供自定义快捷键和附属界面。

![MioKit 插件管理](assets/images/plugin-index.png)

### 设置与个性化

MioKit 支持主题模式、主题色、开机启动、全局快捷键、搜索结果管理和插件管理等设置。完整功能说明请查看[功能介绍](docs/features.md)。

## 文档

### 面向普通用户

- [用户指南](docs/user-guide.md)：安装、首次启动、快捷开始和插件安装。
- [功能介绍](docs/features.md)：了解搜索、Command、快捷键和插件扩展能力。
- [浏览 MioKit 插件](https://www.tinyisle.cn/plugins)：查看可用插件及其安装信息。

### 面向开发者

- [开发者文档总览](docs/developer/README.md)：了解开发流程、文档顺序和项目边界。
- [插件开发指南](docs/developer/plugin-development.md)：创建、开发、验证和发布 MioKit 插件。
- [插件清单说明](docs/developer/plugin-manifest.md)：了解 `plugin.json` 的字段和校验规则。

需要完整文档索引时，请查看[文档总览](docs/README.md)。

## 帮助与社区

- [问题反馈](.github/ISSUE_TEMPLATE/bug_report.md)
- [功能建议](.github/ISSUE_TEMPLATE/feature_request.md)
- [贡献指南](docs/contributing.md)
- [MioKit 官网](https://www.tinyisle.cn/)

## 技术栈

<details>
  <summary>查看项目使用的技术</summary>

- [.NET 10](https://dotnet.microsoft.com/)
- [Avalonia UI](https://avaloniaui.net/)
- [Vue 3](https://vuejs.org/)
- [WebView2](https://developer.microsoft.com/microsoft-edge/webview2/)

常驻搜索入口使用 Avalonia 构建，配置页、管理页等需要快速迭代的界面使用 Vue 3 与 WebView2 构建。

</details>
