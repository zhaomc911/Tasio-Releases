# Tasio

支持中文和英文的个人任务应用。

## 下载公开测试版

[下载 Tasio 1.0.0-beta.2](https://github.com/zhaomc911/Tasio-Releases/releases/tag/v1.0.0-beta.2)

| 系统 | 安装包 | 安装方式 |
| --- | --- | --- |
| Windows 10 / 11 x64 | `Tasio-1.0.0-beta.2-windows-x64-setup.exe` | 运行安装器，从开始菜单打开 |
| macOS 12+，Intel / Apple Silicon | `Tasio-1.0.0-beta.2-macos-universal.zip` | 解压，将 Tasio.app 拖入“应用程序” |

下载页的 Source code 归档不是应用安装包。Android、iOS 安装包暂未发布。

Windows 默认安装到 `%LOCALAPPDATA%\Programs\Tasio`，无需管理员权限，可在 Windows 应用设置中卸载。卸载保留用户数据。
Windows 免费测试版没有 Authenticode 代码签名证书，可能出现未知发行者或 SmartScreen 提示；启用 Smart App Control 或组织限制的电脑可能无法运行。请核对来源及 SHA256，参见 [Microsoft 说明](https://learn.microsoft.com/windows/apps/package-and-deploy/smartscreen-reputation)。

macOS 测试版未经 Developer ID 签名和 Apple 公证，首次打开可能需要确认信任；请按 [Apple 说明](https://support.apple.com/zh-cn/102445) 操作。

对应平台的 SHA256SUMS 文件可核对下载完整性。两个公开安装包均已匿名下载并核对哈希。

## 功能

默认展示未完成任务；中文默认、英文切换；紧凑编辑器、任务备注、标签背景分类、日期和可选的 24 小时制时间、可不指定时刻的周期任务；头像更换、搜索及可收起和调整宽度的侧栏。尚未实现系统通知提醒。

## 应用内更新

macOS 使用 Sparkle，Windows 使用 WinSparkle。初始化时及之后每 4 小时调度检查，尊重自动检查偏好；账户菜单也有“检查更新”。需要网络，不是实时推送。

发现后续版本时提示下载，验证 Ed25519 更新包签名，用户确认后安装并重启。更新前先保存编辑中的任务。Ed25519 更新签名不等于 Apple 公证或 Windows Authenticode 签名。

[macOS 更新清单](https://raw.githubusercontent.com/zhaomc911/Tasio-Releases/main/appcast.xml) · [Windows 更新清单](https://raw.githubusercontent.com/zhaomc911/Tasio-Releases/main/appcast-windows.xml)

## 已验证范围

Windows 构建环境的 41 项 Flutter 测试、原生 Release 编译、安装、启动及卸载检查通过。公开 EXE 的 SHA256 与 CI 构建一致，Ed25519 自验及独立篡改检测通过。Windows 用户电脑上的首次下载、登录同步和版本间升级仍待完整试用验证。

macOS 已通过真实 GitHub 更新源从构建号 2 下载、安装并重启到 3，原有登录和任务保留；另一台 Mac 的首次下载流程仍待验证。

## 反馈

请在 [Issues](https://github.com/zhaomc911/Tasio-Releases/issues) 提交系统版本、Tasio 版本及重现步骤。请勿上传密码、登录令牌或私人任务内容。

本仓库用于安装包、发行说明和更新清单。
