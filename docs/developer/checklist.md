# 插件提交检查清单

在用户安装、分发或提交插件包前，由 Agent 完成可自动化检查，再由开发者完成目标环境和发布信息确认。

## Agent 与工程检查

- [ ] Agent 已按工作区状态选择 `miokit-plugin-new`、`miokit-plugin-core` 或所需 UI Skill。
- [ ] 新项目由 `create_plugin` 创建，未手写骨架、未覆盖已有 `plugin/plugin.json`。
- [ ] `check_dev_environment` 通过；WebView2 项目的 Runtime 已满足要求。
- [ ] 所有新 TypeId、EAV `WithId` 等稳定标识均由 `generate_guid` 生成。
- [ ] `validate_plugin_json` 无 errors，且清单未包含 `pluginVersion`、`releaseState` 或 `releaseDate`。
- [ ] 已使用 `pack_plugin` 生成带 `PackageVersion` 的包，且默认验包未被关闭。
- [ ] `inspect_plugin_nupkg` 无 errors；入口 DLL、图标、私有依赖和 WebView2 前端产物（如适用）均符合包布局要求。

## 功能与兼容性

- [ ] 插件功能、使用场景和支持的 MioKit 宿主版本有清晰说明。
- [ ] 已确认依赖的插件、运行时和宿主能力。
- [ ] 不依赖未公开或不稳定的内部 API。
- [ ] 插件可正常加载、停用和卸载，并释放订阅、计时器、窗口、文件句柄和其他外部资源。
- [ ] 已处理加载失败、依赖缺失和配置损坏等情况。

## 安全、发布与文档

- [ ] 包内不包含密钥、令牌、个人路径或调试日志。
- [ ] 已说明网络访问、文件访问和其他外部能力需求。
- [ ] 已在目标宿主环境安装并验证通过验包的包。
- [ ] 已提供安装、使用、卸载说明和版本变更说明。
- [ ] 已由用户决定并完成上传、市场提交或其他分发操作。
