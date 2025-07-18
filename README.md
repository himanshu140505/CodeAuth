# ⚡ CodeAuth: AI & Plagiarism Detection CLI Tool

> 🧠 A fully indigenous, high-speed, CLI-based tool to detect AI-generated code and plagiarism in files, folders, or GitHub repositories.

---

## 🚀 Features

- ✅ Detects if code/content is **AI-generated** with confidence %
- 🔍 Checks for **code plagiarism** using structural & fuzzy logic
- 📁 Accepts files, folders, raw code, and **GitHub repo URLs**
- ⚡ Fast, lightweight, no paid APIs — fully offline-capable
- 🛠 Built from scratch — 100% open, customizable, and extendable

---

## 📂 Folder Structure

```bash
codeauth/
│
├── data/
│   ├── ai_samples/              # Labeled AI-generated content for training
│   ├── human_samples/           # Labeled human-written content for training
│   ├── cleaned/                 # Cleaned training data
│   └── sources/                 # Codebase to compare against for plagiarism
│
├── models/
│   ├── ai_detector.pkl          # Trained AI detection model
│   └── vectorizer.pkl           # Vectorizer used (e.g., TF-IDF)
│
├── utils/
│   ├── preprocessor.py          # Code/content cleaning & normalization
│   ├── file_handler.py          # File and folder operations
│   ├── web_scraper.py           # (Optional) For future page scraping
│   ├── repo_cloner.py           # Clones GitHub repos and extracts files
│   ├── logger.py                # Logging/debugging helper
│   └── ast_parser.py            # AST-based code similarity checker
│
├── engine/
│   ├── ai_detector.py           # AI content classifier
│   ├── plagiarism_checker.py    # Plagiarism engine (SimHash + AST)
│   └── analyzer.py              # Central engine managing full analysis
│
├── main.py                      # 🚀 CLI entry point
├── train_model.py               # Model training script
└── README.md                    # 🔥 This documentation
📌 Usage
🔧 Installation


git clone https://github.com/himanshu140505/codeauth
cd codeauth
pip install -r requirements.txt
⚠️ Make sure git is installed (for GitHub repo scanning)

 🧪 Run Examples
🔹 File Scan
python main.py --file path/to/code.py

🔹 Folder Scan
python main.py --folder path/to/codebase/

🔹 GitHub Repo Scan
python main.py --url https://github.com/username/repo

🔹 Raw Code Input
python main.py --text "def foo(): return 42"

🧠 How It Works
Component	Role
ai_detector.py	Loads ai_detector.pkl model and returns AI-generated %
plagiarism_checker.py	Uses SimHash & AST comparison to return plagiarism %
analyzer.py	Orchestrates preprocessing, AI check, plagiarism scan
repo_cloner.py	Clones GitHub repo and extracts valid source files
preprocessor.py	Normalizes code: removes comments, renames variables
ast_parser.py	Compares code logic using Abstract Syntax Trees

🔍 Output Example
$ python main.py --url https://github.com/username/repo

[+] Cloning https://github.com/username/repo.git...
[✓] Extracted 5 supported source files.

📄 File: main.py
   → AI Confidence: 81%
   → Plagiarism Score: 44%
   → Matched Source: /sources/sample.py

📄 File: utils/handler.py
   → AI Confidence: 9%
   → Plagiarism Score: 69%
   → Matched Source: /sources/legacy_handler.py

---
📊 Summary:
   AI-generated files: 2/5 (40%)
   Plagiarized files: 3/5 (60%)

🧬 Model Training
🔁 Dataset
Place training data in:
/data/ai_samples/
/data/human_samples/

⚙️ Train the AI Classifier
python train_model.py
Outputs:
    models/ai_detector.pkl
    models/vectorizer.pkl

Uses: TF-IDF + Logistic Regression (fast and interpretable)

✨ Features Planned for Later
✅ Web GUI (React or Electron)
✅ Real-time internet plagiarism checks
✅ Multi-language AST (via Tree-sitter)

🔒 Privacy & Ownership
🛡 100% local — nothing is sent to any external API

🧪 Ideal for researchers, students, reviewers, developers


🧠 "In an AI-powered world, know the origin of your code."
— CodeAuth
