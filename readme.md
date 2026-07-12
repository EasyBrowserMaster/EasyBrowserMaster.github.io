# EasyBrowser

[简体中文](readme.md) | [English](README_EN.md)

EasyBrowser 基于 C++ 源代码级指纹防护能力构建，面向自动化、多账号运营、隔离测试等场景设计。通过单浏览器实例承载多个独立 Tab 容器，让每个标签页都拥有独立的指纹、代理和数据空间。

支持平台：![Windows](https://img.shields.io/badge/Windows-0078D6?logo=windows&logoColor=white) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?logo=ubuntu&logoColor=white) ![macOS Apple Silicon](https://img.shields.io/badge/macOS%20Apple%20Silicon-000000?logo=apple&logoColor=white) <a href="https://easybrowser.pages.dev/"><img src="https://img.shields.io/badge/%E4%B8%8B%E8%BD%BD-EasyBrowser-2ea44f" alt="下载 EasyBrowser" /></a>

## 核心亮点

| 能力 | 说明 |
| --- | --- |
| 页签级隔离 | 每个 Tab 对应一个独立容器，指纹、Cookie、代理互不污染 |
| 官方对齐 | 对齐 Google Chrome 主流版本特征与闭源组件 |
| 深度指纹防护 | 覆盖 Canvas、WebGL、AudioContext、WebRTC、Worker、虚拟机等检测点 |
| 代理支持 | 支持 HTTP、SOCKS5 及账密认证代理 |
| 流量控制 | 支持 JS、CSS 代理分流，节省 80%+ 流量 |
| 加载优化 | 可按需禁用图片、字体等高流量资源，提高加载速度并节省内存 |
| AI MCP | 支持通过 [EasyBrowserMCP](https://github.com/EasyBrowserMaster/EasyBrowserMCP) 接入 AI 自动化工作流，便于环境管理、任务编排与浏览器控制 |
| 资源占用优化 | 多容器共享浏览器实例，降低多账号并发时的内存消耗 |

## 隔离能力

EasyBrowser 的核心设计不是简单复制多个浏览器窗口，而是在一个浏览器实例内实现多个独立容器。

- 数据隔离：Cookie、LocalStorage、IndexedDB 等站点数据按 Tab 隔离
- 指纹隔离：语言、时区、分辨率、WebGL、Canvas、Audio、WebRTC、语音列表、Worker 指纹独立生成
- 代理隔离：每个 Tab 独立出站代理，动态切换不影响其他环境

| 场景 | 平台 | 测试结果 |
| --- | --- | --- |
| 指纹检测 | browserscan | ✅ 全部通过 |
| 指纹检测 | creepjs | ✅ 全部通过 |
| 指纹检测 | fingerprintjspro | ✅ 全部通过 |
| 风控测试 | reCAPTCHA v3 | ✅ 0.9 |
| 风控测试 | Cloudflare 验证 | ✅ 成功 |
| 风控测试 | hCaptcha 验证 | ✅ 成功 |
| 平台测试 | 微软邮箱注册 | ✅ 成功 |
| 平台测试 | TikTok 注册 | ✅ 成功 |
| 平台测试 | GitHub 注册 | ✅ 成功 |

### 部分测试截图

<p align="center">
  <img src="case/case-1.png" alt="EasyBrowser 检测结果 1" width="90%" />
</p>

<p align="center">
  <img src="case/case-2.png" alt="EasyBrowser 检测结果 2" width="90%" />
</p>

<p align="center">
  <img src="case/case-3.png" alt="EasyBrowser 检测结果 3" width="90%" />
</p>

<p align="center">
  <img src="case/case-4.png" alt="EasyBrowser 检测结果 4" width="90%" />
</p>

## 使用声明与免责声明

EasyBrowser 仅面向合法、合规的技术研究、自动化测试、账号环境隔离、隐私保护和开发调试场景。

使用者在下载、安装、运行或分发本项目时，应自行确认使用目的、使用方式和使用环境符合所在地法律法规、监管要求以及目标网站或平台的服务条款。

### 合规用途

本项目可用于以下合法场景：

- 个人隐私防护与浏览环境隔离
- 经授权、合规的账号与店铺环境管理
- 浏览器自动化能力学习与研究
- 指纹一致性、环境隔离与兼容性测试
- 经授权的安全研究、风控测试和开发调试
- 合法、合规、非盈利的个人研究与技术交流

### 禁止用途

禁止将 EasyBrowser 用于以下行为，包括但不限于：

- 违反当地法律法规、公序良俗或平台规则的行为
- 攻击、骚扰、批量滥用、恶意注册、撞库、刷量、垃圾信息等行为
- 未经授权访问、控制、采集、处理或传播第三方数据
- 规避平台安全机制后实施违法、违规或侵害他人权益的行为
- 采集法律法规、平台条款或 Robots 协议明确禁止采集的数据
- 任何可能损害他人、平台、系统或公共网络安全的行为

### 责任声明

使用 EasyBrowser 所产生的一切行为、数据、风险、纠纷和法律后果，均由使用者自行承担。

版权持有人不对因使用、误用或无法使用 EasyBrowser 所导致的任何直接或间接损失承担责任，包括但不限于账号限制、数据损失、业务中断、第三方索赔或法律责任。

如使用者违反上述声明或相关法律法规，版权持有人有权停止授权，并保留依法追究责任的权利。
