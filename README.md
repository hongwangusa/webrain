# WeBrain (微信大脑) · 本地微信回复起草与高情商润色助手

<p align="center">
  <img src="https://raw.githubusercontent.com/hongwangusa/webrain/main/assets/banner.png" alt="WeBrain Banner" width="720" onerror="this.style.display='none'"/>
</p>

<p align="center">
  <a href="https://github.com/hongwangusa/webrain/releases"><img src="https://img.shields.io/github/v/release/hongwangusa/webrain?color=blue&label=Release" alt="Latest Release"></a>
  <a href="#"><img src="https://img.shields.io/badge/Platform-Windows%2010%2B-brightgreen" alt="Platform"></a>
  <a href="#"><img src="https://img.shields.io/badge/Architecture-Keyless%20%7C%20Local--Only-orange" alt="Architecture"></a>
  <a href="#"><img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License"></a>
  <a href="#"><img src="https://img.shields.io/badge/PRs-Welcome-brightgreen.svg" alt="PRs Welcome"></a>
</p>

<p align="center">
  <b>国内首款基于原生辅助视角的非侵入式微信回复起草工具。</b><br>
  零封号风险 · 纯本地运行 (127.0.0.1) · 免安装 (~13MB) · 自带 Key / 本地私有模型支持 · 告别职场沟通内耗
</p>

---

[English Readme](#english-documentation) | [中文说明文档](#中文说明文档) | [快速上手](#快速上手) | [首启配置指南](#首启配置向导说明) | [安全与隐私声明](#安全与隐私承诺) | [问卷与反馈](#用户反馈与社区交流)

---

## 中文说明文档

### 💡 为什么需要 WeBrain？

每天面对密密麻麻的微信消息，你是否也经历过这些时刻：
- **向上汇报**：项目卡壳想向领导求助，生怕言辞不当显得没有担当？
- **婉拒请求**：同事朋友提出不合理或超负荷的需求，如何体面拒绝而不伤人脉？
- **客户沟通**：突发紧急交付延期，如何真诚解释并给出补救方案，安抚客户情绪？
- **跨部门协同**：措辞如何既讲清事实、推动进度，又避免语气生硬激化矛盾？

市面上现有的所谓"微信 AI 机器人"或"智能客服助手"，绝大多数采用 **逆向 iPad/Mac 协议、Hook 注入微信进程、接管账号自动发消息** 的高危方案。个人微信没有开放接口，使用此类工具极易触发微信风控，**导致账号被封禁数天至永久封号**。

**WeBrain 的路线完全不同：它不碰你的微信，只做你的"本地草稿本"。**

```
传统高危机器人方案：
[ 逆向协议 / DLL 注入 ] ---> [ 接管微信号 ] ---> [ 自动回消息 ] ❌ (极高封号风险)

WeBrain 安全辅助方案：
[ 你的初步想法 ] ---> [ WeBrain 本地 WebUI (127.0.0.1) ] ---> [ 大模型生成 3 版得体措辞 ]
                                                                      │
                                                             [ 用户亲自挑选并复制 ]
                                                                      │
                                                             [ 粘贴至微信正常发送 ] ✅ (零封号风险)
```

---

### ✨ 核心特性

- 🛡️ **绝对的零封号风险（Zero-Ban Risk）**：
  不注入内存、不逆向协议、不接管微信号，绝不自动代发消息。所有发送均由用户手动完成，对微信服务端而言即是纯正的真人打字。
- 💻 **免安装 & 极速轻量**：
  发布包解压后仅约 13.5MB，纯绿色便携式设计，解压即用，不写系统注册表，不写启动项。
- 🔒 **纯本地回环运行（Local Loopback）**：
  核心服务严格绑定在 `127.0.0.1:18980`（后台模式绑定 `18981`），绝不监听局域网公网 IP（`0.0.0.0`），坚决防范局域网嗅探。
- 🔑 **Keyless 纯净架构（BYO-Key）**：
  软件内 **0 预埋商业密钥、0 预置 Token 追踪**（经过全二进制及 CArchive 安全解包静态扫描）。你的 API Key 直接保存在本机本地配置文件中，与大模型服务商端到端通信。
- 🧠 **内置多厂商预设 & 本地模型支持**：
  - 深度适配主流中文模型：**智谱 GLM**、**硅基流动 (SiliconFlow)**、**DeepSeek**、**月之暗面 Kimi**；
  - 兼容任意 OpenAI 格式自定义接口；
  - **原生支持本地私有大模型**：可填入本地 Ollama (`http://127.0.0.1:11434/v1`) 或 llamafile，100% 离线脱机运行，绝密沟通不出内网。
- 🎯 **内置丰富沟通场景模板**：
  提供一键切换模板：向上汇报、委婉推脱、客户公关、请假调休、长辈问候等。

---

### 🚀 快速上手

#### 步骤 1：下载解压
从下方渠道下载最新的公测构建包：
- **国内高速直链（推荐，免梯子）**：[蓝奏云下载](https://wwx.lanzoux.com/[TODO-LANZOU-ID]) (密码: `[TODO-LANZOU-PWD]`) / [123云盘下载](https://www.123pan.cn/s/[TODO-123PAN-ID])
- **GitHub Release 官方镜像**：[下载 WeBrain-Online-Beta-v3-wizard.zip](https://github.com/hongwangusa/webrain/releases/latest)

解压 `WeBrain-Online-Beta-v3-wizard.zip` 到任意英文路径文件夹下（例如 `D:\Tools\WeBrain`）。

#### 步骤 2：启动软件
- **普通模式**：双击运行 `start.bat`（会保留控制台窗口，方便查看实时日志）。
- **无窗口静默模式**：双击运行 `start.vbs`（后台静默运行，无黑窗闪烁）。
- 启动后浏览器将自动打开本地交互界面：`http://127.0.0.1:18980`。

#### 步骤 3：首启向导（Wizard）
第一次启动且未检测到配置时，系统会自动弹出 3 步初始化向导：
1. **选择服务商**：从下拉列表中选择你常用的模型服务商（智谱、硅基流动、DeepSeek、Kimi 等）。
2. **输入 API Key**：粘贴你在对应厂商控制台申请的 API Key（若选用本地 Ollama，点击"使用本地模型"并填写本地地址）。
3. **连通性测试**：点击【测试连接】，绿灯通过后点击【保存并开始使用】。

---

### ⚙️ 常用模型厂商 Key 获取与配置参考

| 服务商 | 推荐模型型号 | 特点与免费额度参考 | 接口地址 (Base URL) |
|---|---|---|---|
| **智谱清言 (BigModel)** | `glm-4-flash` | 新用户免费额度高，中文语境极佳，推理极速 | `https://open.bigmodel.cn/api/paas/v4` |
| **硅基流动 (SiliconFlow)** | `deepseek-ai/DeepSeek-V3` | 赠送充值代金券，聚合多款顶级开源模型 | `https://api.siliconflow.cn/v1` |
| **DeepSeek (深度求索)** | `deepseek-chat` | 逻辑强、措辞自然，性价比业界标杆 | `https://api.deepseek.com/v1` |
| **月之暗面 (Moonshot Kimi)** | `moonshot-v1-8k` | 上下文理解优异，适合长消息归纳起草 | `https://api.moonshot.cn/v1` |
| **本地 Ollama (私有离线)** | `qwen2.5:7b` / `llama3.1:8b` | **完全免费、100% 离线脱网、数据彻底留本机** | `http://127.0.0.1:11434/v1` |

> *注：API Key 获取属于各开放平台自主政策，首次注册大多赠送数百万至数千万免费 Token，足够个人日常回复起草使用数月。*

---

### 🔒 安全与隐私承诺（Zero-Fabrication 验证）

1. **零埋点 / 零遥测**：代码中不存在 Google Analytics、百度统计、Sentry 或任何第三方遥测 SDK。
2. **零数据留存**：你的草稿输入与生成的回复，仅通过你配置的 API 发送至你选定的模型提供商，WeBrain 服务端本身不缓存、不上报任何文本。
3. **进程沙箱与隔离**：WeBrain 绝不读取系统注册表中的 WeChat 数据目录，绝不扫盘读取用户的本地文件。
4. **包体哈希校验**：
   - 官方构建文件：`WeBrain-Online-Beta-v3-wizard.zip`
   - 文件大小：13,505,821 字节 (~13.5MB)
   - SHA-256 校验和：`7D5A3E3197FF5BA537A55C09F257912E8B9DE1B1A5ECFE4F64D7FE4C4E2D669A`

---

### ❓ 常见问题排查（FAQ）

#### Q1: 提示端口冲突或者打开网页报错 18980 无法访问？
A: 检查是否有其他进程占用了 18980 端口。可在命令行执行 `netstat -ano | findstr 18980` 查看占用进程；或改用 `start.vbs` 启动备用端口 18981。

#### Q2: Windows Defender / SmartScreen 提示"未知发布者"拦截？
A: 由于公测版发布包尚未购买昂贵的企业 EV 签名证书，Windows 会默认弹出风险提示。点击【更多信息】 -> 【仍要运行】即可。如心存顾虑，欢迎使用解压工具查看包内源码结构或自行在隔离环境中测试。

#### Q3: 为什么不提供"一键自动发送到微信"的功能？
A: 这是 WeBrain 的底线设计。自动发送需要调用 Windows UI 模拟甚至句柄操作微信主窗口，极易与微信防脚本风控产生摩擦；由人工审核最后一眼并手动点击发送，既是对自己的职场形象负责，更是 100% 杜绝封号的唯一解。

---

<br>

---

## English Documentation

### 💡 What is WeBrain?

**WeBrain** is a non-invasive, ultra-lightweight Windows desktop assistant designed to help professionals and everyday users compose polished, considerate, and context-aware replies for WeChat and other messaging workflows.

Instead of adopting risky reverse-engineered protocols or hooking into native messaging processes, **WeBrain acts strictly as an external, secure scratchpad**. You provide your rough thought, WeBrain prompts modern LLMs to craft multiple well-worded drafts (polite, direct, humorous, corporate), and you choose, inspect, copy, and send manually.

### 🌟 Key Highlights
- **100% Ban-Free**: Zero process injection, zero protocol reverse-engineering, zero automated message transmission.
- **Local & Private**: Web UI runs strictly on loopback interface (`127.0.0.1:18980`). No telemetry, no usage tracking, no remote data aggregation.
- **BYO-Key & Local Model Ready**: Completely keyless release. Bring your own API key (DeepSeek, Zhipu, SiliconFlow, Kimi, OpenAI) or hook it up directly to an offline Ollama instance (`http://127.0.0.1:11434/v1`).
- **Zero Installation**: Portable 13.5MB zip package. Just extract and run.

### 📦 Quick Start
1. Download `WeBrain-Online-Beta-v3-wizard.zip` from [Releases](https://github.com/hongwangusa/webrain/releases).
2. Extract to any local directory.
3. Launch `start.bat` (console mode) or `start.vbs` (silent background mode).
4. The first-launch wizard will open automatically at `http://127.0.0.1:18980`. Set up your LLM provider in 30 seconds and start drafting!

---

## 用户反馈与社区交流

WeBrain 仍处于积极迭代的 Public Beta 公测阶段，我们非常渴望倾听真实用户的实际体验！
- 📝 **公测体验问卷（1 分钟）**：[填写腾讯问卷反馈](https://wj.qq.com/s2/[TODO-SURVEY-ID]/)
- 🐛 **提交 Bug 或需求**：欢迎提交 [GitHub Issues](https://github.com/hongwangusa/webrain/issues)
- 💬 **反馈快捷键**：在软件界面右上角点击【帮助与反馈】，可一键生成当前环境配置信息，方便快速排障。

---

## 📜 开源协议与免责声明 (License & Disclaimer)

本项目基于 [MIT License](LICENSE) 开源。

**免责声明**：WeBrain 为独立的本地文本辅助起草工具，与腾讯公司（Tencent Holdings Ltd.）或微信（WeChat）无任何从属、投资、合作或背书关系。用户使用本工具调用第三方大语言模型服务时产生的 API 资费与数据流转规则，由用户与对应大模型提供商依据其服务条款直接确立。
