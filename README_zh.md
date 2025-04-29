---

# 🧠 Lyra：多模态 AI 助手

Lyra 是一个支持**语音与文字双向交互**的多模态虚拟助手项目。  
项目集成了 OpenAI Whisper 语音识别、LLaMA GGUF（Q4量化）语言生成模型，以及 Microsoft Edge TTS 语音合成技术，旨在提供自然流畅的人机对话体验。

---

## 🚀 快速开始

### 1. 克隆项目仓库

```bash
git clone https://github.com/your-username/lyra.git
cd lyra
```

### 2. 创建运行环境

确保已安装 [Miniconda](https://docs.conda.io/en/latest/miniconda.html)。

```bash
conda env create -f environment.yml
conda activate lyra
```

### 3. 下载 LLaMA GGUF 模型

从 Hugging Face 下载量化版 OpenHermes 模型：

```bash
mkdir -p ./models/OpenHermes/
wget https://huggingface.co/TheBloke/OpenHermes-2.5-Mistral-7B-GGUF/resolve/main/openhermes-2.5-mistral-7b.Q4_K_M.gguf -O ./models/OpenHermes/openhermes-2.5-mistral-7b.Q4_K_M.gguf
```

> 或可手动将 `.gguf` 文件置于 `./models/OpenHermes/` 目录下。

### 4. 启动网页应用

```bash
python web_app.py
```

在浏览器中访问 [http://127.0.0.1:5000](http://127.0.0.1:5000) 开始交互。

---

## 📦 核心依赖

- `flask` —— 轻量级网页框架
- `whisper` —— 自动语音识别（ASR）
- `edge-tts` —— Microsoft Edge 语音合成
- `llama-cpp-python` —— 高效推理 LLaMA GGUF 模型
- `ffmpeg` —— 音频处理工具（Whisper依赖）

---

## 💡 功能亮点

- **多模态交互**：支持文本输入与语音输入，智能判断输出形式（文本或语音）。
- **自然语音体验**：语音回复以气泡形式展示，配备播放与文字转写功能。
- **高效本地部署**：在消费级 GPU（如 RTX 3060，推荐 12GB 显存及以上）上流畅运行。

---

## 📍 项目结构

```
lyra/
├── web_app.py
├── environment.yml
├── history.txt
├── README.md
├── README_zh.md
├── .gitignore
│
├── models/
│   ├── asr_model.py
│   ├── chat_model.py
│   ├── tts_model.py
│   └── OpenHermes/
│       └── openhermes-2.5-mistral-7b.Q4_K_M.gguf  # 如有，手动放置
│
├── static/
│   ├── audio/               # 存放语音文件
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── main.js
│
├── templates/
│   └── index.html
│
└── utils/
    ├── emotion.py
    └── persona.py

```

---

## 📢 免责声明

Lyra 是一个实验性开源项目，旨在探索语音与文字多模态交互的技术路径。  
欢迎根据自身需求自由扩展与定制。

---