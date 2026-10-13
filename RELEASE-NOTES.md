# Literature OS v6.3-t · Windows 内测版

本次 v6.3-t 更新打通了 Zotero 分层文献库与多 PDF 同步、APA/GB/T 7714 引用及导出，修复了安装路径问题，并已完成实机测试及 Zotero 联动测试。以 **Pre-release** 发布，旧版 v6.2-t 的标签、Release 和附件保留。

## 更新内容

- **Zotero 本机只读连接**：支持个人库、群组库、整库或选定集合；预览题录、集合和附件数量。保留集合父子层级、空集合、同名集合、多集合归属与未分类题录；重复同步保持稳定身份，保留手动导入功能。
- **手动与自动同步**：支持立即同步、完整核对、取消及中断后重试。自动同步默认关闭，开启后在启动时同步并每 60 秒检查，仅在程序运行期间工作。来源更新不覆盖本地字段修订，冲突可逐字段处理；来源删除后保留本地题录、缓存 PDF 和引用身份。
- **多个 PDF 附件**：复制本机可读 PDF，核对 SHA-256 并按内容去重；展示缺失、无效及来源删除状态。可切换主 PDF，后台 worker 提取全文。检索索引针对主 PDF，附加 PDF 切为主 PDF 后索引；不含 OCR。无 PDF 题录仍可引用。
- **引用样式**：新增 APA 第 7 版、GB/T 7714-2025 顺序编码和 GB/T 7714-2015 兼容样式，保留原有基础格式。每篇文稿独立保存样式；正文引用与文末列表使用随包离线提供的 citeproc/CSL，支持组合引用、页码定位、同作者同年区分、重复引用和排序。
- **编辑与导出**：插入、移动、删除、撤销和重做保持引用关联；Word、LaTeX、PDF 共用格式化结果。旧文稿默认基础格式；手写普通 `[1]` 不自动转换，手写 LaTeX 引用和自定义参考文献环境保留并提示复核。
- **数据保护与兼容**：备份、恢复及复制迁移支持多个附件、来源范围和同步状态；保留阅读检索、富文本/LaTeX 写作、教学示例及 DeepSeek、OpenAI 兼容、Claude、Gemini 四种 BYOK 服务。关于页面反馈邮箱更新为 alvinyu0922@gmail.com。
- **安装修复**：标准 Windows Installer 修复读取原自选安装路径，避免写回默认目录；显式指定的新安装路径仍优先。v6.3-t 使用独立的安装身份及默认资料目录，可与旧版并存。

## 下载与迁移

- [Windows x64 MSI 安装包](https://github.com/SihongYu0922/literature-os-beta/releases/download/v6.3-t/LiteratureOS-v6.3-t-Windows-x64.msi)：41,409,261 字节。
- [桌面 / 本机网页版便携 ZIP](https://github.com/SihongYu0922/literature-os-beta/releases/download/v6.3-t/LiteratureOS-v6.3-t-Portable-Web-Desktop.zip)：41,217,457 字节。
- [SHA256SUMS.txt](https://github.com/SihongYu0922/literature-os-beta/releases/download/v6.3-t/SHA256SUMS.txt)：安装前核对下载文件。
- [旧版 v6.2-t](https://github.com/SihongYu0922/literature-os-beta/releases/tag/v6.2-t)：继续保留下载。

安装前退出应用。便携包解压后双击“启动桌面版.cmd”或“启动网页版.cmd”。无需购买或激活；AI 需自行配置 API Key，相应服务费用由自己的模型账户承担。

新版数据结构为 schema 3。迁移旧资料时，先在旧版建立整库备份，再恢复到新的空目录，让新版打开该副本；保留原资料和备份，勿让旧版打开已经升级的数据目录。

连接 Zotero 前，在 Zotero 设置 → 高级启用“允许本机其他应用通信”。本版为 Zotero → Literature OS 单向同步，只复制本机可读 PDF，不写回 Zotero；不包含云附件自动下载、PDF 批注同步或双向同步。

显示版本 **6.3-t**，npm **6.3.0-t**，MSI ProductVersion **6.3.0**。默认资料目录为 `D:\LiteratureOS\TestData\v6.3-t`。桌面需要 Windows x64、.NET Framework 4.8 与 WebView2 Runtime；PDF 编译需要本机 TeX。GitHub 自动生成的 Source code 压缩包仅含发行说明和宣传图，请下载 MSI 或便携 ZIP。

## 验证与已知限制

- 本地最终回归 **149/149 通过，0 失败、0 跳过**，包含正常 Windows 用户环境下的 DPAPI 验证。
- 便携包独立运行、多个附件切换和全文索引、引用导出与 Word/PDF 渲染通过；本机 MSI 安装、标准修复、卸载均退出 0，安装及修复后 337/337 载荷文件哈希一致。
- 分发审计通过：ZIP CRC、340 个文件路径、337 个载荷哈希、凭据模式及运行数据排除；667 个 v6.2-t 基线文件和 6 个旧交付文件保持不变。
- 已完成实机测试及 Zotero 联动测试（发布者确认）。自动化验证另覆盖官方 API 行为构造的合成场景、本地 PDF 操作及 2,500 条合成题录；合成规模测试不作为真实大库性能指标。
- 安装包和程序未做代码签名。
- 引用样例通过不等于 GB/T 全条款认证；GB 页码包含本地 citation layout 扩展，缺失题录及用户手写 LaTeX 仍需人工核对。随包提供引擎与样式的上游信息、完整许可文本及资源校验清单。

反馈请在看到宣传推文的平台联系，或发送至 [alvinyu0922@gmail.com](mailto:alvinyu0922@gmail.com)，注明软件版本、Windows 版本和复现步骤。请勿发送 API Key、私人 PDF、完整文献库或数据库。

---

# Literature OS v6.2-t · Windows 内测版

公开内测发行，标记为 **Pre-release**。保留现有本地文献阅读、关键词与原文联动、引用、富文本及 LaTeX 写作、导出、教学示例和备份恢复功能。

## 下载与使用

- MSI：Windows x64 安装包，39,802,092 字节。
- ZIP：桌面 / 本机网页版便携包，39,605,505 字节。
- SHA256SUMS.txt：核对安装包与便携包是否完整。

无需购买、激活或联系开发者即可使用此内测版。AI 功能使用测试者自己的 DeepSeek、OpenAI 兼容、Claude 或 Gemini 配置，服务调用费用由各自模型账户承担。首次启动为空白配置，API Key 按服务通过当前 Windows 用户的 DPAPI 加密保存。

独立应用身份和默认资料目录，可与旧版本并存；安装前退出正在运行的应用。请先使用内置教学资料，重要数据另行备份。本机 Node/SQLite 服务仅监听 127.0.0.1。

发行标识：显示版本 **v6.2-t**，npm **6.2.0-t**，MSI ProductVersion **6.2.0**。

## 验证与已知限制

116 项回归中，115 项在沙箱通过，1 项 DPAPI 测试在正常 Windows 用户环境复测通过；便携 ZIP CRC、发行文件哈希、逐文件清单和常见密钥模式检查通过。

安装包与主程序未签名；干净 Windows 机器的安装、修复、卸载矩阵尚未完成。WiX 反编译检查出现安装向导控件引用警告，向导仍需实机验收。真实模型账户的连通性与计费尚未核验。桌面需要 .NET Framework 4.8 / WebView2 Runtime，PDF 编译需要 TeX。

本版本用于内测，不代表正式生产发行。有 Bug 或优化建议，请在看到宣传推文的平台反馈，或发送邮件至 [alvinyu0922@gmail.com](mailto:alvinyu0922@gmail.com)。请注明版本与操作步骤，不要发送私人文献、科研数据、数据库、日志或 API Key。

本仓库只作为公开下载渠道，已关闭 Issues、Pull Request、Wiki 和提交评论；普通访客没有上传、修改文件或替换安装包的权限。
