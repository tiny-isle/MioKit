# 开发者文档

本目录面向通过 AI Agent 创建、开发、验证和分发 MioKit 插件的开发者。项目创建与工程检查统一使用 [MioKit.CodeAgent](https://github.com/tiny-isle/MioKit.CodeAgent)：[Skill](https://skills.sh/tiny-isle/MioKit.CodeAgent) 提供约定与选型，[`@tiny-isle/miokit-mcp`](https://www.npmjs.com/package/@tiny-isle/miokit-mcp) 提供环境检查、创建、校验、打包和验包。

首次使用建议先阅读[插件开发指南](plugin-development.md)中的 Skill 安装和 MCP 配置说明。

## 推荐阅读顺序

1. [插件开发指南](plugin-development.md)：安装前提、Agent 路由和创建到交付的主流程。
2. [插件清单说明](plugin-manifest.md)：`plugin.json` 的最小字段、版本规则与 MCP 校验。
3. [调试、打包与发布](debugging-and-packaging.md)：验包边界与目标宿主验证。
4. [插件提交检查清单](checklist.md)：交付前的自动化与人工确认项。
5. [架构设计](architecture.md)：理解宿主、节点树、Feature 与 UI 的协作边界。

## 工作边界

Agent 不手写插件骨架，也不直接运行模板安装或 `dotnet new`；新项目应调用 CodeAgent 的 `create_plugin`。打包完成后必须通过 `inspect_plugin_nupkg`，才可交给用户安装或发布。

CodeAgent 的 Skill 和 MCP schema 是 SDK/API 约定的权威来源。本目录只保留稳定的开发流程和验收要求；节点、生命周期、EAV、搜索、Avalonia 和 WebView2 的细节请按需读取相应 Skill。
