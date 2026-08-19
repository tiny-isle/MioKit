# 插件清单说明

`plugin/plugin.json` 描述插件身份、入口程序集和 MioKit SDK 兼容范围。创建模板会生成初始清单；修改后应由 Agent 调用 `validate_plugin_json` 校验，而不是手工猜测字段或版本格式。

完整 schema 以 CodeAgent MCP resource `miokit://plugin-json-schema` 和 `miokit-plugin-core` Skill 为准。

## 最小有效清单

以下字段均为非空字符串且必填：

| 字段 | 用途 |
| --- | --- |
| `metadataVersion` | 清单格式版本 |
| `id` | 稳定的插件唯一标识 |
| `name` | 插件显示名称 |
| `assembly` | 包根目录中的插件入口 DLL 文件名 |
| `minSdkVersion` | 最低兼容 SDK 版本 |

```json
{
  "metadataVersion": "1.0",
  "id": "com.contoso.plugin.my-plugin",
  "name": "My Plugin",
  "assembly": "MyPlugin.dll",
  "minSdkVersion": "1.0.0"
}
```

`id` 推荐使用 `com.<组织>.plugin.<短名>` 格式。未确定时，Agent 应先调用 `suggest_plugin_id`，或在 `create_plugin` 中提供 `org` 让工具生成建议值。

## 版本规则

`minSdkVersion` 以及可选的 `maxSdkVersion`、`minHostVersion`、`maxHostVersion` 必须使用 .NET `System.Version` 格式：`major.minor[.build[.revision]]`。例如 `2.0.0` 有效，`2.0.0-beta.1` 无效。

插件发布版本由 NuGet `PackageVersion` 承载，可使用例如 `1.2.0` 或 `1.3.0-beta.1` 的 SemVer。清单中不得出现下列旧发布字段：

- `pluginVersion`
- `releaseState`
- `releaseDate`

## 校验流程

1. 让 Agent 修改模板生成的 `plugin/plugin.json`。
2. 要求 Agent 调用 `validate_plugin_json` 并处理所有 errors。
3. 打包前再次校验；`pack_plugin` 随后的验包还会确认清单、入口 DLL 和资源在 `.nupkg` 中的位置一致。

清单还可声明图标和依赖等内容。字段语义、私有依赖规则和包内资源约定应直接参照 CodeAgent 的 `miokit-plugin-core` Skill，避免在本站维护重复规范。

## 相关文档

- [插件开发指南](plugin-development.md)
- [调试、打包与发布](debugging-and-packaging.md)
- [MioKit.CodeAgent](https://github.com/tiny-isle/MioKit.CodeAgent)
