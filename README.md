<div align="center">

# 🚄 12306 火车票票根编辑器

*纯前端 · 单文件 · 零依赖 · 数据不出浏览器*

![Version](https://img.shields.io/badge/version-6.2.4-2E7CF6)

![License](https://img.shields.io/badge/license-MIT-green)

![Dependencies](https://img.shields.io/badge/dependencies-0-success)

![Runtime](https://img.shields.io/badge/runtime-浏览器%20Canvas-9B59B6)

一个 12306 风格的火车票票根编辑器：填写行程信息即可实时生成以假乱真的车票正面与背面，  
支持六款票面底图、模块级细节精修、12306 行程 PDF 智能导入与多行程管理，可一键导出图片。

**🚀 在线使用**：<https://ajietudou007.github.io/12306-train-ticket-editor/?v=6.2.4>

> 💡 链接自带版本参数 `?v=6.2.4` 以绕过 CDN / 浏览器缓存。若页面仍显示旧版本，请强制刷新（`Cmd/Ctrl + Shift + R`）。

</div>

> **⚠️ 免责声明**  
> 本项目仅供**个人纪念与娱乐创作**使用（如收藏票根、短视频道具、同人创作等）。  
> 与中国国家铁路集团（12306）无任何隶属或合作关系。  
> 严禁将生成的票面用于报销、退票、逃票、诈骗或其他任何违法违规用途，由此产生的一切后果由使用者自行承担。

---

## ✨ 界面展示
<img width="3360" height="1932" alt="image" src="https://github.com/user-attachments/assets/00f19c8f-0337-42f3-8181-6b6eff6e76e9" />
<img width="3360" height="1932" alt="image" src="https://github.com/user-attachments/assets/32f16c4b-a511-4ceb-bf87-cd715dfea3c6" />
<img width="3360" height="1932" alt="image" src="https://github.com/user-attachments/assets/2d390022-e6de-46ce-8905-756343cb156f" />
<img width="3360" height="1932" alt="image" src="https://github.com/user-attachments/assets/8f965b93-b55a-4cad-a58f-8964ea6b7dbf" />
<img width="3360" height="1932" alt="image" src="https://github.com/user-attachments/assets/cffa1091-ff5c-4a35-bc2b-4d8e4bd10fc8" />
<img width="3360" height="1932" alt="image" src="https://github.com/user-attachments/assets/c7fedcb4-0a13-48d6-af86-492c09e5f571" />

## ✨ 功能特性

- **六款票面底图**：蓝票 / 蓝纸票 / 蓝磁票 / 红票 / 红纸票 / 红磁票，正面与背面独立选用，底图全部内嵌（Base64），离线可用
- **车票背面制作**：报销凭证「使用须知」模板，背景与遮罩可自定义，支持正反面合并导出
- **模块级细节调整**：18 个票面模块（票号、检票口、站名、车次、二维码……）支持位置微调、字号（50%～200%）、字间距、文字粗细与**字体**（5 种系统字体 + 导入 TTF/WOFF/WOFF2 自定义字体）的独立精修，并按票种独立记忆
- **模块多选与批量对齐**：多选模块后可一键水平对齐、底部对齐、居左、居中、居右
- **多行程同步渲染**：一个行程完成细节调整后，自动同步到其余所有行程并重新渲染
- **12306 行程 PDF 智能导入**：拖入官方「行程信息提示」PDF，自动解析并回填站名 / 车次 / 日期 / 座位 / 金额等字段；手动修改优先，空白不覆盖已填内容
- **纸质车票照片 OCR 识别**：拍照 / 扫描件自动透视矫正 + 方向转正 + 标准票幅裁剪后识别回填；支持本地引擎（PP-OCRv6 / v5 / Tesseract）与 AI 引擎（Agnes 3.0 Flash，内置 Key 开箱即用），联网引擎仅在明确确认后使用；识别结果可一键生成车票或导出 CSV
- **智能联想**：站点 / 车次输入联想补全，站名拼音自动联动
- **导出便捷**：单张直接下载 PNG，多张自动打包 ZIP；导出文件名按「车次_日期_站名」规范命名；触屏设备支持长按保存图片，兼容夸克 / UC 等移动内核
- **本地持久化与分享**：行程数据 JSON 序列化（LZ-String 压缩 → URL），刷新不丢失，可生成携带数据的分享链接
- **明暗双主题**：铁路信号台设计语言，全套自绘图标

## 🚀 快速开始

本项目是一个**零构建、零依赖的单文件应用**，无需安装任何包。

### 方式一：直接打开

下载 `index.html` 后用现代浏览器双击打开即可使用。

### 方式二：本地服务（推荐）

```bash
# 使用 npm
npm start                # 即 python3 -m http.server 8080

# 或直接
python3 -m http.server 8080
# 打开 http://127.0.0.1:8080
```

### 方式三：GitHub Pages

仓库入口即 `index.html`，在 **Settings → Pages** 中选择 `main` 分支根目录后，  
即可通过 `https://<用户名>.github.io/<仓库名>/` 在线访问。

## 📖 使用指南

1. **填写行程** — 在左侧表单录入车站、车次、日期、座位、票价等信息；或直接拖入 12306 行程 PDF 自动回填
2. **挑选底图** — 在正面预览区切换六款票面，背面画布同理；点击「背面制作」可自定义背面
3. **细节精修（可选）** — 点击「细节调整」打开悬浮窗，单击票面任意模块后微调其位置 / 字号 / 间距 / 粗细；支持多选批量对齐；所有调整随行程自动保存
4. **导出保存** — 单张直接下载，多张自动打包 ZIP；也可以用「分享链接」把整份数据编码进 URL 发给朋友
5. **管理行程** — 支持多条行程独立编辑（数据深拷贝隔离），刷新后逐程还原

> 💡 所有数据仅保存在本地浏览器与分享链接中，**没有任何网络请求上传**。

## 📁 项目结构

```text
GitHub火车票编辑器/
├── index.html      # 应用本体（V6.2.4，含全部样式 / 脚本 / 内嵌底图资源）
├── README.md
├── CHANGELOG.md    # 版本日志（V4.0 → V6.2.4）
├── LICENSE         # MIT
├── package.json    # 仅用于 npm start 一键启动本地服务
└── .gitignore
```

> 历史版本以单文件快照形式在开发目录中留存，未纳入本仓库；本仓库始终以 `index.html` 承载最新稳定版。

## 🛠 技术实现

- **技术栈**：原生 HTML / CSS / JavaScript，Canvas 2D 绘制管线，无框架、无构建步骤
- **单文件架构**：六款底图（压缩后约 4.3MB → 0.5MB）与全部图标以内嵌 Base64 / SVG 形式打包，离线即开即用
- **绘制内核**：`redraw()` 统一重绘 + 票种级排版覆盖表（`LAYOUT_ADJ`）+ 模块级调整表（`__MODULE_ADJ`），ctx 实例级补丁实现偏移 / 缩放 / 间距 / 字重而零默认开销
- **PDF 解析**：内嵌 Mozilla pdf.js 相关组件（Apache-2.0）解析 12306 官方行程 PDF
- **数据压缩**：内嵌 LZ-String 将行程数据压缩进 URL，支持旧格式回退兼容

## 🌐 浏览器兼容

| 浏览器                     | 支持情况      |
| ----------------------- | --------- |
| Chrome / Edge（Chromium） | ✅ 推荐使用最新版 |
| Safari                  | ✅ 最新版     |
| Firefox                 | ✅ 最新版     |

需要支持 Canvas 2D 与 `FileReader` / `DataTransfer` API 的现代浏览器；不再维护 IE。

## 🔒 隐私说明

本项目**不包含任何统计、追踪或上传逻辑**：表单数据、PDF 内容、导出图片全部在你的浏览器本地完成处理。  
通过「分享链接」保存数据时，数据以压缩字符串形式编码在 URL 的 Hash 部分中，同样不会经过任何服务器。

## 📋 版本日志

完整修改记录见 [CHANGELOG.md](CHANGELOG.md)，也可在应用右上角「更新日志」按钮内查看。

## 🤝 参与贡献

欢迎 Issue 与 PR！

1. Fork 本仓库并新建分支（`git checkout -b feature/your-feature`）
2. 修改 `index.html`（保持单文件架构，勿引入构建步骤或外部运行时依赖）
3. 提交变更（`git commit -m "feat: xxx"`）并发起 Pull Request
4. 提交前请自测：明暗双主题、六款底图切换、正反面渲染与导出均应正常

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源，第三方内嵌组件的许可声明保留在 `index.html` 源码内：

- [pdf.js](https://github.com/mozilla/pdf.js) — Mozilla Foundation，Apache License 2.0
- [LZ-String](https://github.com/pieroxy/lz-string) — 数据压缩
