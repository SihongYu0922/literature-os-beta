# Literature OS · Windows 内测版

![Literature OS：把阅读，连成思路。](media/literature-os-beta-banner.png)

从文献到原文，从原文到写作。Literature OS 把本地文献阅读、关键词与原文联动、引用和写作放在同一个工作区。

当前版本 **v6.4-t**，面向 Windows x64 的内测发行。宣传图中的书页与内容为视觉示意。

## 下载

- [v6.4-t 下载页与更新说明](https://github.com/SihongYu0922/literature-os-beta/releases/tag/v6.4-t)
- [Windows x64 MSI 安装包](https://github.com/SihongYu0922/literature-os-beta/releases/download/v6.4-t/LiteratureOS-v6.4-t-Windows-x64.msi)
- [桌面 / 本机网页版便携 ZIP](https://github.com/SihongYu0922/literature-os-beta/releases/download/v6.4-t/LiteratureOS-v6.4-t-Portable-Web-Desktop.zip)
- [SHA-256 校验文件](https://github.com/SihongYu0922/literature-os-beta/releases/download/v6.4-t/SHA256SUMS.txt)

[历史版本 v6.3-t](https://github.com/SihongYu0922/literature-os-beta/releases/tag/v6.3-t) 与 [v6.2-t](https://github.com/SihongYu0922/literature-os-beta/releases/tag/v6.2-t) 的安装包、便携包和校验文件继续保留。

首次使用推荐 MSI；需要便携目录时选择 ZIP。Releases 页自动生成的 “Source code” 压缩包仅包含本仓库的宣传和说明文件，不是软件安装包。

## v6.4-t 更新

Zotero 同步和手动批量导入均按每批最多 200 MB 在后台自动连续处理；单个大 PDF 分块后保留完整文件，并校验 SHA-256，提供批次进度与取消操作。文件失败后继续后续文件，索引失败时保留 PDF。

159/159 自动化测试通过，覆盖桌面、Zotero 与网页 201 MB 跨批处理，以及真实 PDF 上传和索引。保留 v6.3-t 的分层集合、多附件、离线 APA/GB/T 7714 引用与导出、安装修复功能。详细变更见 [RELEASE-NOTES.md](RELEASE-NOTES.md)。

请保持程序或网页打开直至导入完成；手动导入不支持关闭后的断点续传。MB = 1024 × 1024 字节。

## 开始使用

1. 下载后与 SHA256SUMS.txt 核对；安装前退出正在运行的应用。
2. 安装或解压，启动时选择新的资料目录。先用内置教学资料体验功能，再导入自己的资料。
3. 此内测版无需购买、激活或联系开发者即可使用。AI 功能需自行配置模型服务的 API Key，相应调用费用由所选服务按自己的账户计费。

支持各自配置 DeepSeek、OpenAI 兼容、Claude 或 Gemini；不要向任何反馈入口发送 API Key、私人 PDF 或完整文献库。

迁移 v6.3-t 或更早版本资料前先备份，再恢复到新的空目录；新版 schema 3 资料勿交给旧版打开。Zotero 自动同步默认关闭，启用后仅在应用运行期间检查；本版不写回 Zotero。此前 v6.3-t 已完成实机测试及 Zotero 联动测试（发布者确认）。

桌面需要 .NET Framework 4.8 与 WebView2 Runtime；PDF 编译需要本机 TeX。安装包和主程序尚未签名。v6.4-t 已通过构建、打包校验与桌面启动验证；此前 v6.3-t 的安装、修复与卸载验证已完成。

PowerShell 校验示例：

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\LiteratureOS-v6.4-t-Windows-x64.msi
```

显示版本 v6.4-t，npm 版本 6.4.0-t，MSI ProductVersion 6.4.0。安装包作为 Releases 附件分发；本仓库存放发行说明、校验值和宣传图。

## 反馈

有 Bug 或优化建议，请在看到宣传推文的平台反馈，或发送邮件至 [alvinyu0922@gmail.com](mailto:alvinyu0922@gmail.com)。请注明软件版本、Windows 版本、操作步骤，可附脱敏截图；不要发送私人 PDF、完整文献库、数据库、日志或 API Key。

（本 GitHub 仓库仅作为公开下载渠道）
