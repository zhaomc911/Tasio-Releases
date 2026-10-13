# Tasio

Tasio 是一款支持中文和英文的个人任务应用。

## 下载 macOS 公开测试版

[下载 Tasio 1.0.0-beta.1](https://github.com/zhaomc911/Tasio-Releases/releases/tag/v1.0.0-beta.1)

支持 macOS 12 及以上，Apple Silicon 和 Intel 通用。下载 Assets 中的 `Tasio-1.0.0-beta.1-macos-universal.zip`；GitHub 自动生成的 Source code 归档不是应用安装包。

1. 解压 ZIP，将 `Tasio.app` 拖入“应用程序”。
2. 从“应用程序”打开 Tasio。
3. 本测试版未经 Apple Developer ID 签名及 Apple 公证。若系统阻止打开，请先确认文件来自本仓库且未被改动，再按 [Apple 的说明](https://support.apple.com/zh-cn/102445) 在“系统设置 → 隐私与安全性”中选择“仍要打开”。受管理的电脑可能不允许打开。

下载页提供 SHA256SUMS.txt，可核对文件完整性。首次下载的 Gatekeeper 流程尚未在另一台 Mac 上验证。
Windows、Android、iOS 安装包暂未发布。

## 功能

中文默认、英文切换；任务备注、标签、日期和 24 小时制时间、周期任务；头像更换、搜索及可收起侧栏。尚未实现系统通知提醒。

## 应用内更新

macOS 已集成 Sparkle。启动后后台检查，之后每 4 小时调度检查，尊重自动检查偏好；也可在账户菜单选择“检查更新”。检查需要网络，不是实时推送。

发现后续版本时，应用提示下载，验证 Ed25519 更新包签名，用户确认后安装并重启。首次安装仍需按上面的步骤操作。

本机已验证从构建号 2 下载、安装并重启到本公开包的构建号 3，原有登录及任务保留。安装包已匿名下载并核对 SHA256。Apple 的发行签名、公证与 Sparkle 更新包签名用途不同。

[更新清单](https://raw.githubusercontent.com/zhaomc911/Tasio-Releases/main/appcast.xml)

## 反馈

请在 [Issues](https://github.com/zhaomc911/Tasio-Releases/issues) 提交系统版本、Tasio 版本及重现步骤。请勿上传密码、登录令牌或私人任务内容。

本仓库用于安装包、发行说明和更新清单。
