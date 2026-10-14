# Tasio

支持中文和英文的个人任务应用。

## 下载公开测试版

[下载 macOS 1.1.0-beta.1](https://github.com/zhaomc911/Tasio-Releases/releases/tag/v1.1.0-beta.1) · [下载 Windows 1.0.0-beta.3](https://github.com/zhaomc911/Tasio-Releases/releases/tag/v1.0.0-beta.3)

| 系统 | 安装包 | 安装方式 |
| --- | --- | --- |
| Windows 10 / 11 x64 | `Tasio-1.0.0-beta.3-windows-x64-setup.exe` | 运行安装器，从开始菜单打开 |
| macOS 12+，Intel / Apple Silicon | `Tasio-1.1.0-beta.1-macos-universal.zip` | 解压，将 Tasio.app 拖入“应用程序” |

下载页的 Source code 归档不是应用安装包。Android、iOS 安装包暂未发布。

Windows 默认安装到 `%LOCALAPPDATA%\Programs\Tasio`，无需管理员权限，可在 Windows 应用设置中卸载。卸载保留用户数据。
Windows 免费测试版没有 Authenticode 代码签名证书，可能出现未知发行者或 SmartScreen 提示；启用 Smart App Control 或组织限制的电脑可能无法运行。请核对来源及 SHA256，参见 [Microsoft 说明](https://learn.microsoft.com/windows/apps/package-and-deploy/smartscreen-reputation)。

macOS 测试版未经 Developer ID 签名和 Apple 公证，首次打开可能需要确认信任；请按 [Apple 说明](https://support.apple.com/zh-cn/102445) 操作。

对应平台的 SHA256SUMS 文件可核对下载完整性。两个公开安装包均已匿名下载并核对哈希。

## 功能

默认展示未完成任务；中文默认、英文切换；紧凑编辑器、任务备注、标签背景分类、日期和可选的 24 小时制时间、可不指定星期和时刻的周期任务；头像更换、搜索及可收起和调整宽度的侧栏。尚未实现系统通知提醒。

macOS 1.1.0-beta.1 增加紧凑主界面、可交互的简易模式，以及 macOS 14+ 的三种尺寸系统桌面小组件。简易模式可滚动查看任务、输入添加、勾选完成，并与完整窗口互相切换。账户与设置 → 简易模式；点击 Dock 图标恢复当前模式。打开并登录一次后，从桌面右键“编辑小组件”搜索 Tasio。系统小组件请求随任务变化刷新，实际刷新时机由 macOS 调度。Cmd+Q 会退出后台应用。

Windows 桌面组件和简易模式尚未发布，将在后续完成测试。

## 应用内更新

macOS 使用 Sparkle，Windows 使用 WinSparkle。初始化时及之后每 4 小时调度检查，尊重自动检查偏好；账户菜单也有“检查更新”。需要网络，不是实时推送。

发现后续版本时提示下载，验证 Ed25519 更新包签名，用户确认后安装并重启。更新前先保存编辑中的任务。Ed25519 更新签名不等于 Apple 公证或 Windows Authenticode 签名。

[macOS 更新清单](https://raw.githubusercontent.com/zhaomc911/Tasio-Releases/main/appcast.xml) · [Windows 更新清单](https://raw.githubusercontent.com/zhaomc911/Tasio-Releases/main/appcast-windows.xml)

## beta.3 同步修复

头像图片保存在仅本人可访问的独立账号资料表，避免图片进入登录令牌导致请求头过大。旧版头像已保留迁移；新版会刷新受影响会话并重试待上传任务。本机真实账号已验证上传队列清空、云端拉取成功、登录和头像保留。尚未覆盖另一台电脑上 beta.2 到 beta.3 的完整自动升级流程。

## 已验证范围

Windows 构建环境的 43 项 Flutter 测试、原生 Release 编译、安装、启动及卸载检查通过。公开 EXE 的 SHA256 与 CI 构建一致，Ed25519 自验及独立篡改检测通过。Windows 用户电脑上的首次下载、登录同步和版本间升级仍待完整试用验证。

macOS 1.1.0-beta.1 的 47 项 Flutter 测试及静态检查通过，公开 ZIP 已匿名下载并核对 SHA256，更新包 Ed25519 签名自验通过。本机桌面交互已试用；另一台 Mac 首次安装和本次跨版本自动升级尚待验证。系统小组件暂采用只读专用快照目录共享展示信息，不含认证令牌、账号标识或备注，尚未迁移到 App Groups。

macOS 已通过真实 GitHub 更新源从构建号 2 下载、安装并重启到 3，原有登录和任务保留；另一台 Mac 的首次下载流程仍待验证。

## 反馈

请在 [Issues](https://github.com/zhaomc911/Tasio-Releases/issues) 提交系统版本、Tasio 版本及重现步骤。请勿上传密码、登录令牌或私人任务内容。

本仓库用于安装包、发行说明和更新清单。
