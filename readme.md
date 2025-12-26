Certainly! Here's a professional and clear **English README.md** for your Zed extension that integrates Qwen Code:

---

# Qwen Code for Zed

[![Zed Extension](https://img.shields.io/badge/Zed-Extension-5F5FD6?logo=zed&logoColor=white)](https://zed.dev)
[![License](https://img.shields.io/github/license/yourname/qwen-code-zed)](LICENSE)

Bring the power of **Qwen Code**—Alibaba Cloud’s AI-powered coding assistant—directly into [Zed](https://zed.dev), the high-performance code editor. This extension enables intelligent code completion, natural language programming, and context-aware suggestions using the official Qwen Code CLI via Zed’s Agent Control Protocol (ACP).

> ✨ **No setup required beyond installation**—once installed, Zed automatically downloads and runs the Qwen agent.

---

## ✨ Features

- 🧠 **AI-powered code completions** with Qwen’s state-of-the-art code models
- 💬 **Chat-based coding assistance** in Zed’s right-side panel
- 📁 **Project-aware context**: reference files with `@filename`
- 🔒 **Secure & private**: runs locally; API requests go directly to DashScope (no proxy)
- 🌐 **Multi-platform support**: macOS (Intel & Apple Silicon), Linux, Windows

---

## 🛠 Requirements

- [Zed](https://zed.dev) v0.150 or later
- [Node.js](https://nodejs.org/) v20 or later (required to run the Qwen CLI agent)
- A **DashScope API key** from Alibaba Cloud ([get one here](https://dashscope.console.aliyun.com/apiKey))

> 💡 The first time you use the agent, you’ll be prompted to log in or set your API key.

---

## 📦 Installation

1. Open Zed
2. Press `Cmd/Ctrl + Shift + P` to open the command palette
3. Type **“Extensions: Install Extension”**
4. Search for **“Qwen Code”**
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

This extension uses Zed’s **Agent Control Protocol (ACP)** to communicate with the official [`@qwen-code/qwen-code`](https://github.com/QwenLM/qwen-code) CLI tool:

- The agent is distributed as an **npm `.tgz` package**
- Zed downloads and unpacks it automatically
- It runs: `node ./package/cli.js --experimental-acp`
- All communication happens over **stdin/stdout** using JSON-RPC

No telemetry. No cloud proxy. Just direct integration with Qwen.

---

## 📂 Project Structure

```
qwen-code-zed/
├── extension.toml        # Zed extension manifest
├── README.md
└── LICENSE
```

The actual agent logic lives in the official Qwen Code npm package—this extension only provides the glue for Zed.

---

## 🤝 Contributing

Contributions are welcome! If you’d like to:

- Improve platform support
- Add settings UI (e.g., model selection)
- Enable local LLM backends (Ollama, vLLM)

Please open an issue or submit a PR.

---

## 📜 License

This extension is licensed under the [MIT License](LICENSE).  
The underlying `qwen-code` CLI is developed by [Alibaba Tongyi Lab](https://github.com/QwenLM).

---

## 🙏 Acknowledgements

- Inspired by [CodeBuddy for Zed](https://github.com/jasonwang82/codebuddy-code-zed)
- Built on [Qwen Code](https://github.com/QwenLM/qwen-code) by Alibaba
- Powered by [Zed’s Agent System](https://zed.dev)

---

> Made with ❤️ for developers who love AI-assisted coding.

---

✅ **Replace `yourname`** in the badge and repository links with your actual GitHub username.  
✅ Update the **Installation** section once your extension is published to the Zed registry (or provide manual install instructions if self-hosted).

Let me know if you'd like a **Chinese version**, a **screenshot guide**, or help setting up **GitHub Actions for auto-releases**!