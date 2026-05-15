# EasyBrowser

> 🚧 **即将发布，内测中** — 如需内测资格，请联系我们 https://t.me/rainabcde

基于定制 Chromium 的**页签级隔离**指纹浏览器，专为自动化场景设计。

---

## 核心优势

直击自动化三大痛点：**内存消耗、流量消耗、机器人检测 & 指纹检测**。

一个浏览器实例运行多个完全隔离的容器（Tab），并发无需多开浏览器。

---

## 容器设计

- 一个 Tab 对应一个容器，Tab 可随时切换容器
- 每个容器独立指纹、Cookie、代理，互不干扰
- 并发只需一个浏览器实例，大幅节省系统资源

---

## 容器功能

### 指纹隔离

CPU · 内存 · 语言 · 语音列表 · 时区 · WebRTC · WebGL · Canvas · Audio · Worker等

### 指纹防检测

通过 Browserscan、CreepJS、Pixelscan 等各大主流指纹检测网站。

先进防检测技术：
- JS / Intl / HTTP / Worker 多端一致性处理
- Canvas 渲染层处理：空白检测、噪音检测、多 API 一致性检测
- Audio 内核特征检测
- CSS API 检测

### Cookie / LocalStorage / IndexedDB 隔离

同一浏览器多个 Tab 运行多个账号，数据完全隔离。

### 代理隔离

多 Tab 设置不同代理，每个容器独立出口 IP。

---

## 资源节省

### 节省流量

1. **浏览器缓存共享**：多容器共享静态文件缓存，相同资源只下载一次
2. **源码级代理 Bypass**：基于 Chromium 源码级改造，支持自定义 bypass 规则，静态资源直连不走代理，大幅降低代理流量消耗

### 节省内存

相比传统多实例并发方案，多 Tab 架构至少节省内存 **30%+**。

---

## 与 EasyCDP 配合使用

EasyBrowser 容器功能完整支持 CDP 控制，可通过 [EasyCDP](https://github.com/EasyBrowserDeveloper/EasyCDP) 进行自动化操作：

```python
browser = await EasyBrowserCDP.launch_and_connect(port=9992, executable=r'path\to\fp_chrome.exe')
container = await browser.new_container(name="account-1", fingerprint=fp, proxy="http://user:pass@host:port")
page = await container.new_page("https://example.com")
```