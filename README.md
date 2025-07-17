# PLH211 Coursework Projects 2022‑2023

> Two self‑contained assignments for the *Software Engineering & Operating Systems* course (PLH211, A.Y. 2022‑2023).
>
> *Project 1*: **Python Twitter Viewer & Editor – full development pipeline**
> *Project 2*: **Linux Commands, Bash Scripting & Python Process Control**

---

## Table of Contents

1. [Project 1 – Twitter Viewer & Editor](#project-1)
2. [Project 2 – Linux/Bash & Process Control](#project-2)
3. [Getting Started](#getting-started)
4. [Directory Structure](#directory-structure)
5. [License](#license)

---

## <a id="project-1"></a>Project 1 – Twitter Viewer & Editor *(Python)*

| Phase            | Goal                                                                          | Key Artefacts                               |
| ---------------- | ----------------------------------------------------------------------------- | ------------------------------------------- |
| **Development**  | Build an MVP CLI tool for viewing & editing tweet collections stored as JSON. | `viewer_editor.py` (object‑oriented code)   |
| **Logging**      | Add structured runtime logging (custom `logging` config).                     | `myeditorlog.conf`, log files under `logs/` |
| **Profiling**    | Measure hot‑spots with *line\_profiler* / `cProfile`.                         | `profiling_report.txt`                      |
| **Refactoring**  | Apply idiomatic Python & OOP best‑practices; improve modularity.              | Refactored `viewer/` package                |
| **Unit Testing** | Validate every module & command with **pytest** assertions.                   | `tests/` directory                          |

**Notebook:** `PLH211_Project1_2022_2023.ipynb` — contains detailed narrative, code cells for each phase, and reflective commentary.

### How to run

```bash
# activate env (see below)
python -m viewer_editor tweets.json   # interactive CLI
pytest -q                              # run unit tests
python -m cProfile -m viewer_editor tweets.json  # quick profile
```

---

## <a id="project-2"></a>Project 2 – Linux/Bash & Process Control

| Topic                                           | Deliverable                                                                                                 |
| ----------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Θέμα 1 – Linux Commands**                     | Cheat‑sheet & demo scripts of essential command‑line utilities (`grep`, `awk`, `sed`, pipes, redirection…). |
| **Θέμα 2 – Twitter Viewer & Editor (Bash)**     | Full re‑implementation of the Project 1 CLI entirely in Bash: `twitter_viewer_editor.sh`.                   |
| **Θέμα 3 – Sentiment Analyser (Bash)**          | Pipeline that classifies tweet polarity with simple word‑lists; outputs CSV report.                         |
| **Θέμα 4 – Zig‑Zag Process Generator (Python)** | `zigzag.py` spawns a binary tree of child processes that print their PID & level, up to N levels (*≤10*).   |
| **Θέμα 5 – Three‑Way Pipe (Python)**            | `three_way_pipe.py` demonstrates IPC: a parent coordinates two children via custom duplex pipes.            |

**Notebook:** `PLH211_Project2_2022_2023.ipynb` — showcases shell commands, scripts, and annotated code walkthroughs.

### Quick demos

```bash
bash twitter_viewer_editor.sh tweets.json        # Bash version
bash sentiment_analyser.sh tweets.json           # Produce sentiment_report.csv
python zigzag.py 4                               # 4‑level process tree
python three_way_pipe.py                         # IPC demo
```

---

## Getting Started

### 1. Clone

```bash
git clone <repo‑url>
cd plh211‑projects
```

### 2. Create environment (Python ≥ 3.9)

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt  # pytest, line_profiler, matplotlib, etc.
```

### 3. Launch notebooks *(optional)*

```bash
jupyter lab  # open the .ipynb files for a guided walkthrough
```

> **Note:** Bash scripts are fully POSIX‑compliant and require a standard GNU/Linux shell environment.

---

## Directory Structure

```
.
├── project1/
│   ├── viewer/                 # refactored Python package
│   ├── logs/
│   ├── tests/
│   ├── profiling_report.txt
│   └── PLH211_Project1_2022_2023.ipynb
├── project2/
│   ├── scripts/                # *.sh Bash utilities
│   ├── zigzag.py
│   ├── three_way_pipe.py
│   └── PLH211_Project2_2022_2023.ipynb
├── data/                       # sample tweets.json, wordlists
├── requirements.txt
└── README.md                   # (this file)
```

---

## License

Material provided for educational purposes under the **MIT License**. See `LICENSE` for details.
