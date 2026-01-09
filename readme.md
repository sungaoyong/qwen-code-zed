
# Qwen Code for Zed

[![Zed Extension](https://img.shields.io/badge/Zed-Extension-5F5FD6?logo=zed&logoColor=white)](https://zed.dev)
[![License](https://img.shields.io/github/license/sungaoyong/qwen-code-zed)](LICENSE)

Integrates Qwen Code models into the Zed editor. Provides intelligent code completion, chat-based programming, and context-aware suggestions through the ACP protocol.

Version: 0.6.1

---

## ✨ Features

- 🧠 **AI-powered code completions** with Qwen's state-of-the-art code models
- 💬 **Chat-based coding assistance** in Zed's right-side panel
- 📁 **Project-aware context**: reference files with `@filename`
- 🔒 **Secure & private**: runs locally; API requests go directly to DashScope (no proxy)
- 🌐 **Multi-platform support**: macOS (Intel & Apple Silicon), Linux, Windows

---

## 🛠 Requirements

- [Zed](https://zed.dev) editor
- [Node.js](https://nodejs.org/) (required to run the Qwen CLI agent)
- A **DashScope API key** from Alibaba Cloud ([get one here](https://dashscope.console.aliyun.com/apiKey))

> 💡 The first time you use the agent, you'll be prompted to log in or set your API key.

---

## 📦 Installation

1. Open Zed editor
2. Press `Cmd/Ctrl + Shift + P` to open the command palette
3. Type **"Extensions: Install Extension"**
4. Search for **"Qwen Code"**
5. Click **Install**

Zed will automatically:
- Download the Qwen Code agent package
- Launch it via Node.js in the background
- Activate the AI panel on the right

> ⚠️ Make sure Node.js is installed and available in your system `PATH`.

---

## 🔑 Authentication

On first use, the agent will prompt you to authenticate. You can:

### Option 1: Interactive Login
```bash
# Run in terminal (optional, Zed may prompt automatically)
qwen auth login
```

### Option 2: Set API Key via Environment Variable
Add to your shell profile (`~/.zshrc`, `~/.bashrc`, etc.):
```bash
export DASHSCOPE_API_KEY="sk-xxxxxx"
```
Then restart Zed.

---

## 🧪 How It Works

This extension uses Zed's **Agent Control Protocol (ACP)** to communicate with the official [`@qwen-code/qwen-code`](https://github.com/sungaoyong/qwen-code-zed) CLI tool:

- The agent is distributed as an **npm `.tgz` package**
- Zed downloads and unpacks it automatically
- It runs: `node ./package/cli.js --experimental-acp`
- All communication happens over **stdin/stdout** using JSON-RPC

No telemetry. No cloud proxy. Direct integration with Qwen.

---

## 📂 Project Structure

```
qwen-code-zed/
├── extension.toml        # Zed extension manifest
├── README.md
└── LICENSE
```

The actual agent logic resides in the official Qwen Code npm package—this extension only provides the interface for Zed.

---

## 🤝 Contributing

Contributions are welcome! If you'd like to:

- Improve platform support
- Add settings UI (e.g., model selection)
- Enable local LLM backends (Ollama, vLLM)

Please open an issue or submit a PR.

---

## 📜 License

This extension is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- Inspired by [CodeBuddy for Zed](https://github.com/jasonwang82/codebuddy-code-zed)
- Built on [Qwen Code](https://github.com/QwenLM/qwen-code) by Alibaba Tongyi Lab
- Powered by [Zed's Agent System](https://zed.dev)

---

通义千问代码模型集成到 Zed 编辑器。通过 ACP 协议提供智能代码补全、对话编程和上下文感知建议。

版本: 0.6.1

---

## ✨ 特性

- 🧠 **AI驱动的代码补全** 使用通义千问先进的代码模型
- 💬 **基于对话的编码助手** 在Zed的右侧面板中
- 📁 **项目感知上下文**: 通过 `@filename` 引用文件
- 🔒 **安全私密**: 本地运行；API请求直接发送到DashScope（无代理）
- 🌐 **多平台支持**: macOS (Intel & Apple Silicon), Linux, Windows

---

## 🛠 系统要求

- [Zed](https://zed.dev) 编辑器
- [Node.js](https://nodejs.org/) (运行Qwen CLI代理所必需)
- 阿里云的 **DashScope API 密钥** ([在此获取](https://dashscope.console.aliyun.com/apiKey))

> 💡 首次使用时，系统会提示您登录或设置API密钥。

---

## 📦 安装

1. 打开Zed编辑器
2. 按 `Cmd/Ctrl + Shift + P` 打开命令面板
3. 输入 **"Extensions: Install Extension"**
4. 搜索 **"Qwen Code"**
5. 点击 **安装**

Zed将自动：
- 下载Qwen Code代理包
- 在后台通过Node.js启动
- 在右侧激活AI面板

> ⚠️ 确保Node.js已安装并在系统`PATH`中可用。

---

## 🔑 认证

首次使用时，代理会提示您进行认证。您可以：

### 方式一：交互式登录
```bash
# 在终端中运行（可选，Zed可能会自动提示）
qwen auth login
```

### 方式二：通过环境变量设置API密钥
添加到您的shell配置文件(`~/.zshrc`, `~/.bashrc`等)：
```bash
export DASHSCOPE_API_KEY="sk-xxxxxx"
```
然后重启Zed。

---

## 🧪 工作原理

此扩展使用Zed的 **Agent Control Protocol (ACP)** 与官方的 [`@qwen-code/qwen-code`](https://github.com/sungaoyong/qwen-code-zed) CLI工具通信：

- 代理以 **npm `.tgz` 包**形式分发
- Zed自动下载并解压
- 运行命令: `node ./package/cli.js --experimental-acp`
- 所有通信通过 **stdin/stdout** 使用JSON-RPC进行

无遥测。无云代理。直接与Qwen集成。

---

## 📂 项目结构

```
qwen-code-zed/
├── extension.toml        # Zed扩展清单
├── README.md
└── LICENSE
```

实际的代理逻辑位于官方Qwen Code npm包中——此扩展仅为Zed提供接口。

---

## 🤝 贡献

欢迎贡献！如果您想：

- 改进平台支持
- 添加设置界面（如模型选择）
- 启用本地LLM后端（Ollama, vLLM）

请开启问题或提交PR。

---

## 📜 许可证

本扩展采用 [MIT许可证](LICENSE) 授权。

---

## 🙏 致谢

- 受 [CodeBuddy for Zed](https://github.com/jasonwang82/codebuddy-code-zed) 启发
- 基于阿里通义实验室的 [Qwen Code](https://github.com/QwenLM/qwen-code)
- 由 [Zed的代理系统](https://zed.dev) 提供支持

