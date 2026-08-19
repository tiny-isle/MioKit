# 开源致谢

MioKit 的每一步发展都离不开开源社区的长期投入。感谢以下项目与维护者为桌面界面、运行时、数据处理、插件生态和 Web 前端提供基础能力。本页覆盖仓库当前显式引用的主要运行时、构建与测试依赖；同类的小型辅助包按用途合并列出。

## 桌面界面与交互

1. [SukiUI](https://github.com/kikipoulet/SukiUI)：为 MioKit 的 Avalonia 桌面界面设计与控件实现提供了重要参考。
2. [Avalonia](https://github.com/AvaloniaUI/Avalonia)：跨平台 .NET UI 框架，承载 MioKit 的原生窗口、控件、输入和主题体验；同时使用其 Desktop、诊断、Inter 字体与 Simple 主题组件。
3. [AvaloniaEdit](https://github.com/AvaloniaUI/AvaloniaEdit)、[AvaloniaEdit.TextMate](https://www.nuget.org/packages/AvaloniaEdit.TextMate/)、[Avalonia.Controls.ColorPicker](https://www.nuget.org/packages/Avalonia.Controls.ColorPicker/) 与 [Avalonia DataGrid](https://www.nuget.org/packages/Avalonia.Controls.DataGrid/)：提供编辑器、语法高亮、颜色选择和表格控件。
4. [Lucide](https://github.com/lucide-icons/lucide) 与 [Lucide.Avalonia](https://www.nuget.org/packages/Lucide.Avalonia/)：提供桌面和 Web 界面使用的图标。
5. [SkiaSharp](https://github.com/mono/SkiaSharp)：提供图形渲染能力。
6. [Xaml.Behaviors](https://www.nuget.org/packages/Xaml.Behaviors.Interactions.Events/)：提供 XAML 行为与交互支持。
7. [FlaUI](https://github.com/FlaUI/FlaUI) 与 [H.InputSimulator](https://www.nuget.org/packages/H.InputSimulator/)：支持 Windows 自动化与输入模拟。
8. [WebView2 SDK](https://developer.microsoft.com/microsoft-edge/webview2/)：让 Avalonia 宿主能够承载设置和管理用的 Web 界面。

## .NET 运行时、插件与数据

1. [CommunityToolkit.Mvvm](https://github.com/CommunityToolkit/dotnet)：提供 MVVM 的可观察属性和命令基础设施。
2. [Autofac](https://github.com/autofac/Autofac) 与 [Autofac.Extensions.DependencyInjection](https://github.com/autofac/Autofac.Extensions.DependencyInjection)：用于宿主和插件子容器的依赖注入、服务注册与生命周期管理。
3. [Dapper](https://github.com/DapperLib/Dapper)：轻量的数据访问层，服务于运行时数据读写。
4. [SQLite](https://www.sqlite.org/) 与 [SQLitePCLRaw](https://github.com/ericsink/SQLitePCL.raw)：为本地数据、图标和插件相关存储提供数据库基础能力。
5. [Serilog](https://github.com/serilog/serilog) 及其 [Console](https://www.nuget.org/packages/Serilog.Sinks.Console/) 和 [File](https://www.nuget.org/packages/Serilog.Sinks.File/) sinks：提供结构化日志记录与诊断能力。
6. [MessagePack-CSharp](https://github.com/MessagePack-CSharp/MessagePack-CSharp)、[Json.NET](https://github.com/JamesNK/Newtonsoft.Json) 与 [Mapster](https://github.com/MapsterMapper/Mapster)：用于消息、配置和对象映射。
7. [Microsoft.Extensions](https://github.com/dotnet/runtime) 系列：提供依赖注入、配置、日志、缓存、对象池和 Options 基础设施。
8. [NuGet.Client](https://github.com/NuGet/NuGet.Client)：支持插件包及其依赖的协议和打包处理。
9. [OwlCore.Storage](https://www.nuget.org/packages/OwlCore.Storage/)：提供存储抽象能力。
10. [Vanara](https://github.com/dahall/Vanara) 与 [CsWin32](https://github.com/microsoft/CsWin32)：提供 Windows API、Shell 和互操作封装。
11. [ClearScript](https://github.com/microsoft/ClearScript)：提供脚本运行时支持。
12. [MimeTypeMapOfficial](https://www.nuget.org/packages/MimeTypeMapOfficial/) 与 [System.Linq.Dynamic.Core](https://github.com/StefH/System.Linq.Dynamic.Core)：提供 MIME 类型和动态查询辅助能力。
13. [Windows Community Toolkit Notifications](https://github.com/CommunityToolkit/WindowsCommunityToolkit)：提供 Windows 通知支持。
14. [ObservableCollections](https://github.com/Cysharp/ObservableCollections)：提供高效的可观察集合实现。
15. [.NET System.* 扩展包](https://github.com/dotnet/runtime)：包括 `System.Drawing.Common`、`System.IO.Hashing` 与 `System.Security.Cryptography.ProtectedData`，用于图像、哈希和受保护数据处理。

## Web 前端

1. [Vue.js](https://github.com/vuejs/core)：构建设置、管理等 Web 界面。
2. [Vue Router](https://github.com/vuejs/router)、[Pinia](https://github.com/vuejs/pinia) 与 [VueUse](https://github.com/vueuse/vueuse)：提供路由、状态管理和组合式工具集。
3. [Vite](https://github.com/vitejs/vite) 与 [Vite Vue Plugin](https://github.com/vitejs/vite-plugin-vue)：提供前端开发服务器与构建流程。
4. [Tailwind CSS](https://github.com/tailwindlabs/tailwindcss)、[tailwind-merge](https://github.com/dcastil/tailwind-merge)、[Class Variance Authority](https://github.com/joe-bell/cva) 与 [tw-animate-css](https://www.npmjs.com/package/tw-animate-css)：用于样式、变体和动画。
5. [Reka UI](https://github.com/unovue/reka-ui)、[Vaul Vue](https://www.npmjs.com/package/vaul-vue) 与 [Vue Sonner](https://www.npmjs.com/package/vue-sonner)：提供可组合的 UI 原语、抽屉和通知交互。
6. [TanStack Table](https://github.com/TanStack/table) 与 [TanStack Virtual](https://github.com/TanStack/virtual)：支持设置与管理界面的表格、列表和虚拟滚动。
7. [Monaco Editor](https://github.com/microsoft/monaco-editor) 与 [vite-plugin-monaco-editor](https://www.npmjs.com/package/vite-plugin-monaco-editor)：提供代码编辑器及其构建集成。
8. [DOMPurify](https://github.com/cure53/DOMPurify)、[Marked](https://github.com/markedjs/marked) 与 [favicon-fetcher](https://www.npmjs.com/package/@victr/favicon-fetcher)：用于安全的富文本、Markdown 和网站图标处理。
9. [vue-draggable-plus](https://www.npmjs.com/package/vue-draggable-plus)、[clsx](https://github.com/lukeed/clsx) 与 [Node.js 类型定义](https://www.npmjs.com/package/@types/node)：提供拖拽排序、条件类名与前端开发类型支持。

## 构建、代码生成与测试

1. [Roslyn](https://github.com/dotnet/roslyn)：为 MioKit 的源生成器和编译期分析提供编译器平台。
2. [xUnit.net](https://github.com/xunit/xunit) 与 [coverlet](https://github.com/coverlet-coverage/coverlet)：支持自动化测试和覆盖率收集。
3. [.NET](https://github.com/dotnet/runtime) 与 [NuGet](https://github.com/NuGet/Home)：提供应用运行时、SDK 和包分发基础。

## 许可证与归属

本页仅用于表达感谢，不替代各项目的许可证、版权声明或 NOTICE 文件。MioKit 会在分发和发布时遵守其所使用依赖的适用许可证与归属要求；如有遗漏或需要更正之处，欢迎通过项目反馈渠道告知我们。
