# 调试、打包与发布

插件工程检查由 Agent 通过 MioKit MCP 执行；目标宿主中的安装验证、调试和发布渠道选择仍由开发者负责。两类工作应分开记录，避免把静态验包误认为运行时验证。

## Agent 可执行的工程检查

| 阶段 | MCP 工具 | 通过条件 |
| --- | --- | --- |
| 环境准备 | `check_dev_environment` | 标准插件具备 .NET 10 SDK；WebView2 插件另具备 Runtime |
| 模板准备 | `ensure_plugin_templates` | 官方 NuGet 模板可用，且不是本地文件夹来源 |
| 清单修改后 | `validate_plugin_json` | 清单必填字段、版本格式和禁止字段均通过 |
| 生成稳定标识 | `generate_guid` | TypeId、EAV `WithId` 等不由 Agent 手写 |
| 打包 | `pack_plugin` | 以必填的 `packageVersion` 生成 `.nupkg` |
| 产物检查 | `inspect_plugin_nupkg` | 检查报告没有 errors |

Agent 应使用 `pack_plugin`，并保持其默认的 `inspect: true`。该工具把包输出到解决方案根目录的 `artifacts/`，在验包失败时整体失败；仅有 `.nupkg` 文件不代表交付完成。

## 验包内容

`inspect_plugin_nupkg` 会检查插件包是否满足 MioKit 布局约定，包括：

- 包根目录中的 `plugin.json`，以及其 `assembly` 指向的入口 DLL。
- 图标和其他相对资源是否存在，且包图标与清单图标路径一致。
- 不包含 `MioKit.Sdk.dll`、`MioKit.SourceGenerate.dll`、`MioKit.Webview2.dll` 等宿主共享 DLL。
- 私有依赖 DLL 与 `nugetDependents` 声明不构成双源冲突，也没有独立卸载 DLL、脚本或 SQL。
- WebView2 插件包含已构建的前端静态资源。
- 包描述符合 `miokit.plugin-package` 的元数据信封约定。

收到 errors 时，应把报告交给 Agent 修复工程或清单，再重新打包和验包。warnings 和 hints 用于评估风险，不应用来替代 errors 的修复。

## 目标宿主中的调试与验证

MCP 不连接正在运行的 MioKit 宿主。开发者需要自行在目标环境中完成：

- 安装已通过验包的插件包，并验证加载、核心功能、停用和卸载。
- 记录宿主版本、插件包版本、.NET 运行时版本和完整错误日志。
- 验证插件会释放订阅、计时器、窗口、文件句柄和其他外部资源。
- WebView2 插件还应验证前端资源加载和 .NET/前端桥接。

## 发布边界

`pack_plugin` 和 `inspect_plugin_nupkg` 不会执行 `nuget push`、市场提交或任何上传操作。验包通过后，由用户决定发布到何处、采用何种审核流程，以及如何提供变更说明和用户文档。

## 相关文档

- [插件开发指南](plugin-development.md)
- [插件清单说明](plugin-manifest.md)
- [插件提交检查清单](checklist.md)
