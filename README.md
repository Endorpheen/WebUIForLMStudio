# e0 LLM Chat & WebUI

The **e0 LLM Chat & WebUI** project is a local solution for working with LLM (Large Language Models) in the gguf format. The server is written in **Python** using **FastAPI** and **llama-cpp-python** for generating responses. It also includes an endpoint for text translation using **deep-translator (GoogleTranslator)**. The UI is built with **HTML/CSS/JavaScript** and connects to the server for message exchange.

## Project Structure

```
.
├── llmUI
│   ├── bin/
│   ├── include/
│   ├── lib/
│   ├── lib64/
│   ├── models/
│   │   ├── .gitkeep         # Empty placeholder to track the directory (model files are ignored)
│   │   └── <your .gguf models>  (ignored via .gitignore)
│   ├── pyvenv.cfg
│   ├── server.py            # Main server (FastAPI, llama-cpp-python, deep-translator)
│   └── requirements.txt      # Dependency file
├── webui
│   └── LMStudioWebUI
│       └── lmstudiowebui.html   # UI for LM Studio Chat
├── .gitignore               # Configured to exclude large files (e.g., models)
└── README.md                # This file
```

## Technologies Used

- **Python 3.12+**
- **FastAPI** — backend framework
- **uvicorn** — ASGI server
- **llama-cpp-python** — library for working with gguf models
- **deep-translator** — text translation library (GoogleTranslator)
- **HTML/CSS/JavaScript** — UI

## Requirements

### General:

- Installed **Git**
- Installed **Python 3.12+**
- **llama-cpp-python** may require system libraries (**libgomp**)

### Linux:

```bash
sudo apt update
sudo apt install libgomp1 build-essential
```

### Windows:

- **Python** ([Download](https://www.python.org/downloads/))
- **Visual Studio Build Tools** (if required)

## Installation and Running on Linux

```bash
git clone https://github.com/Endorpheen/WebUIForLMStudio.git
cd WebUIForLMStudio
python3 -m venv llmUI
source llmUI/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
cd llmUI
python server.py
```

The server will start at **[http://0.0.0.0:3005](http://0.0.0.0:3005)**.

**Starting UI:**

```bash
cd webui
python3 -m http.server 8000
```

Open your browser at **[http://localhost:8000/LMStudioWebUI/lmstudiowebui.html](http://localhost:8000/LMStudioWebUI/lmstudiowebui.html)**.

## Installation and Running on Windows

```cmd
git clone https://github.com/Endorpheen/WebUIForLMStudio.git
cd WebUIForLMStudio
python -m venv llmUI
llmUI\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
cd llmUI
python server.py
```

The server will start at **[http://0.0.0.0:3005](http://0.0.0.0:3005)**.

**Starting UI:**

```cmd
cd webui
python -m http.server 8000
```

Open your browser at **[http://localhost:8000/LMStudioWebUI/lmstudiowebui.html](http://localhost:8000/LMStudioWebUI/lmstudiowebui.html)**.

## Usage

- **The UI connects to the server** automatically (**[http://localhost:3005](http://localhost:3005)**).
- **Sending messages:** Enter text and click "Send".
- **Message translation:** Click the "Translate" button to send text to the server.

## Notes

- **Model files** (.gguf) should be placed in `llmUI/models/` (they are ignored by `.gitignore`).
- If **llama-cpp-python** fails to install, ensure you have **libgomp1** and **Visual Studio Build Tools**.
- **Using requirements.txt:**
  - Install all dependencies with one command:
    ```bash
    pip install -r requirements.txt
    ```

## License

The project is distributed under an open license. See the LICENSE file for details.

