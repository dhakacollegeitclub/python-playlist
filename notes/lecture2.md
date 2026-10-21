# Python Course – Lecture 02: Setup, First Program & GitHub (Detailed Note)

> This note covers installing VS Code and Python, verifying the setup, writing and running the first "Hello, World!" program, and a beginner-friendly introduction to GitHub. Every step is explained so you can follow along on your own computer.

---

## Table of Contents

1. Big Picture: What We Are Setting Up and Why
2. Installing VS Code
3. Installing Python
4. Checking the Python Version
5. Setting Up VS Code for Python
6. Your First Program: "Hello, World!"
7. Running Python Code from the VS Code Terminal
8. Understanding What Happened (Behind the Scenes)
9. Introduction to GitHub
10. Pushing "Hello, World!" to GitHub (Step by Step)
11. Common Problems and Fixes
12. Quick Revision
13. Self-Check

---

## 1. Big Picture: What We Are Setting Up and Why

To write and run Python programs, you need three things:

| Tool | What it is | Role |
|---|---|---|
| **Python** | The language and its interpreter | Reads and runs your code |
| **VS Code** | A code editor | Where you write, organize, and run your code comfortably |
| **GitHub** (with Git) | A code hosting platform | Stores your code online and tracks its history |

**Analogy:**
- Python is the **engine** that actually does the work.
- VS Code is the **workshop** where you build things comfortably.
- GitHub is the **storage cabinet in the cloud** where you keep your finished work safe.

**Important:** Python and VS Code are two *separate* programs. Installing VS Code does **not** install Python. You must install both.

---

## 2. Installing VS Code

### What is VS Code?

**Visual Studio Code (VS Code)** is a free, lightweight **code editor** made by Microsoft. It is the most popular editor for Python (and many other languages) because it:

- Is free and works on Windows, macOS, and Linux
- Highlights code in colors (syntax highlighting), making it easier to read
- Suggests code as you type (autocomplete)
- Has a built-in **terminal**, so you can run code without leaving the editor
- Supports thousands of **extensions** to add new features
- Has built-in Git/GitHub support

**Code editor vs IDE (quick note):** A code editor is lighter and more flexible. A full IDE (like PyCharm) has more built-in features but is heavier. VS Code sits in between: a light editor that becomes powerful with extensions.

### Steps to install

1. Open a browser and go to the official website: **https://code.visualstudio.com**
2. The site detects your operating system. Click the main **Download** button (or choose your OS: Windows, macOS, Linux).
3. Run the downloaded installer.
4. On **Windows**, during installation:
   - Accept the license agreement.
   - Choose the install location (the default is fine).
   - On the "Select Additional Tasks" page, it is helpful to tick:
     - **Add "Open with Code" action to Windows Explorer file context menu** (lets you right-click a file or folder and open it in VS Code)
     - **Add to PATH** (usually ticked by default)
5. Click **Install**, wait for it to finish, then click **Finish** (you can launch VS Code right away).
6. On **macOS**: open the downloaded file, drag **Visual Studio Code** into the **Applications** folder.
7. On **Linux**: install the `.deb` or `.rpm` package (or use your distribution's package manager).

> Always download from the official website to avoid fake or unsafe copies.

---

## 3. Installing Python

### Where to download

Always download Python from the **official source: https://www.python.org**

1. Go to **python.org** and open the **Downloads** section.
2. The site shows a button for the latest stable version for your operating system. Click it to download the installer.
3. Choose the latest **Python 3** version. (Python 3 is the standard; Python 2 is obsolete and no longer supported.)

### Installing on Windows (most important steps)

1. Open the downloaded installer (`.exe`).
2. **Very important:** On the first screen, at the bottom, **tick the checkbox "Add python.exe to PATH"** (wording may be "Add Python to PATH").
3. Click **Install Now** (the default option).
4. Wait for the installation to finish and click **Close**.

**What is PATH and why does the checkbox matter?**

PATH is a list of folders that your operating system searches when you type a command in the terminal. If Python's folder is in PATH, typing `python` in the terminal works from anywhere. If you forget to tick the box, the terminal will say it cannot find Python, and you would need to fix PATH manually or reinstall.

### Installing on macOS

1. Download the macOS installer (`.pkg`) from python.org.
2. Open it and follow the installation prompts.
3. After installation, you typically use the command `python3` in the terminal.

### Installing on Linux

- Python 3 is often already installed. You can check with `python3 --version`.
- If not, install it using your package manager (for example, `sudo apt install python3` on Debian/Ubuntu-based systems).

---

## 4. Checking the Python Version

After installing, you should **confirm** that Python is correctly installed.

### Steps

1. Open a terminal:
   - **Windows:** Command Prompt or PowerShell (search for "cmd" or "PowerShell" in the Start menu)
   - **macOS / Linux:** the Terminal application
2. Type one of the following and press **Enter**:

```bash
python --version
```

On macOS/Linux (and sometimes Windows), you may need:

```bash
python3 --version
```

3. You should see output similar to:

```
Python 3.x.x
```

(where `3.x.x` is the exact version you installed).

### Reading the result

- If a version number appears: Python is installed correctly.
- If you get an error like *"python is not recognized as an internal or external command"* (Windows) or *"command not found"*: Python is not in PATH or is not installed. See the Common Problems section.

> You can also use the short form `python -V` (capital V), which gives the same result.

---

## 5. Setting Up VS Code for Python

VS Code works for many languages, so it needs the **Python extension** to understand Python well.

### Install the Python extension

1. Open VS Code.
2. Click the **Extensions** icon in the left sidebar (it looks like four squares), or press `Ctrl + Shift + X` (`Cmd + Shift + X` on macOS).
3. In the search box, type **Python**.
4. Choose the extension published by **Microsoft** and click **Install**.

### What the extension gives you

- Better syntax highlighting and autocomplete
- Error and warning hints while you type
- A **Run** button for Python files
- Support for selecting which Python interpreter to use

### Select the Python interpreter (if needed)

1. Press `Ctrl + Shift + P` (`Cmd + Shift + P` on macOS) to open the **Command Palette**.
2. Type **Python: Select Interpreter** and press Enter.
3. Choose the Python version you installed.

### Basic VS Code layout

| Area | Purpose |
|---|---|
| **Explorer** (left sidebar, top icon) | Shows files and folders of your project |
| **Editor** (center) | Where you write your code |
| **Terminal** (bottom panel) | Where you run commands and see output |
| **Extensions** (left sidebar) | Add features |
| **Source Control** (left sidebar) | Git/GitHub operations |

---

## 6. Your First Program: "Hello, World!"

### Why "Hello, World!"?

"Hello, World!" is the traditional first program in almost every programming language. It is the simplest possible program that proves your setup works: if it prints correctly, your tools are installed and running.

### Step 1: Create a project folder

1. Create a new folder on your computer (for example, `python-course`).
2. In VS Code, go to **File → Open Folder** and select this folder.
   - Working inside a folder keeps your files organized and is required later for GitHub.

### Step 2: Create a Python file

1. In the Explorer panel, click the **New File** icon.
2. Name the file **`hello.py`**.
   - The **`.py`** extension tells VS Code and the computer that this is a Python file.

### Step 3: Write the code

Type the following in the editor:

```python
print("Hello, World!")
```

### Step 4: Save the file

Press `Ctrl + S` (`Cmd + S` on macOS). Always save before running.

### Breaking down the code

| Part | Meaning |
|---|---|
| `print` | A built-in **function** that displays output on the screen |
| `( )` | Parentheses hold what you want to pass to the function |
| `"Hello, World!"` | A piece of text, called a **string**, written inside quotes |
| Quotes `" "` | Tell Python that this is text, not a command. Single quotes `' '` also work |

**Case sensitivity:** Python is case-sensitive. `print` works, but `Print` or `PRINT` will cause an error.

---

## 7. Running Python Code from the VS Code Terminal

There are two common ways to run your program.

### Method 1: Using the integrated terminal (the main method)

1. Open the terminal inside VS Code:
   - Menu: **Terminal → New Terminal**, or
   - Shortcut: `` Ctrl + ` `` (the backtick key, below Esc)
2. Make sure the terminal is in the same folder as your file (opening the folder in VS Code usually does this automatically).
3. Type the command and press **Enter**:

```bash
python hello.py
```

(On macOS/Linux you may need `python3 hello.py`.)

4. Output appears in the terminal:

```
Hello, World!
```

**Command breakdown:**

- `python` → starts the Python interpreter
- `hello.py` → the file you want it to run

### Method 2: The Run button

1. Open `hello.py` in the editor.
2. Click the **Run Python File** (▶) button at the top right of the editor.
3. VS Code opens a terminal and runs the file for you; the output appears there.

### Method 3 (bonus): Interactive mode

You can also type `python` alone in the terminal and press Enter. This opens the **Python interactive shell** (marked by `>>>`) where you can type one line at a time and see results immediately:

```python
>>> print("Hello, World!")
Hello, World!
```

To exit, type `exit()` and press Enter.

---

## 8. Understanding What Happened (Behind the Scenes)

When you ran `python hello.py`, this is what happened:

```
hello.py (your code)
      ↓
Python Interpreter reads it line by line
      ↓
Converts it into instructions the machine understands
      ↓
Computer executes it
      ↓
"Hello, World!" appears in the terminal
```

This connects with the previous lecture: Python is **interpreter-based**, so it reads your code one line at a time and runs it immediately.

---

## 9. Introduction to GitHub

### The problem GitHub solves

Imagine you write code for weeks. What if:

- Your computer crashes and you lose everything?
- You make a mistake and want to return to yesterday's version?
- You want to share your code with others or work in a team?

**Git** and **GitHub** solve these problems.

### Git vs GitHub (a very common confusion)

| | **Git** | **GitHub** |
|---|---|---|
| What it is | A **version control system** (a tool) | An **online platform** (a website/service) |
| Where it lives | Installed on your computer | On the internet (cloud) |
| What it does | Tracks changes to your files over time | Stores your Git projects online and enables sharing and collaboration |

**Analogy:** Git is like a camera that takes snapshots of your project. GitHub is like an online photo album where you store and share those snapshots.

### Key terms

| Term | Meaning |
|---|---|
| **Repository (repo)** | A project folder tracked by Git. It can exist on your computer (local) and on GitHub (remote) |
| **Commit** | A saved snapshot of your project at a point in time, with a message describing the change |
| **Push** | Sending your local commits to GitHub |
| **Pull** | Downloading changes from GitHub to your computer |
| **Clone** | Copying an entire repository from GitHub to your computer |
| **Branch** | A separate line of work (the default is usually `main`) |
| **Remote** | The online copy of your repository (usually named `origin`) |

### Why developers use GitHub

- **Backup:** your code is safe in the cloud
- **Version history:** see and restore earlier versions
- **Collaboration:** many people can work on one project
- **Portfolio:** a public profile that shows your projects to others
- **Open source:** access to millions of public projects

---

## 10. Pushing "Hello, World!" to GitHub (Step by Step)

### Prerequisites

1. A **GitHub account** (free): sign up at **https://github.com**
2. **Git installed** on your computer: download from **https://git-scm.com**
   - Check it with:
   ```bash
   git --version
   ```

### One-time setup: tell Git who you are

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

(Use the same email as your GitHub account.)

### Step 1: Create a new repository on GitHub

1. Log in to GitHub.
2. Click the **+** icon (top right) → **New repository**.
3. Enter a repository name (for example, `python-course`).
4. Choose **Public** or **Private**.
5. Click **Create repository**.
6. GitHub shows a page with the repository URL and setup commands.

### Step 2: Initialize Git in your project folder

Open the VS Code terminal in your project folder and run:

```bash
git init
```

This turns your folder into a Git repository.

### Step 3: Stage your files

```bash
git add .
```

- `git add` moves files into the **staging area** (a waiting area for the next commit).
- The `.` means "all files in this folder."

### Step 4: Commit your changes

```bash
git commit -m "Add Hello World program"
```

- `-m` lets you write a short **message** describing what this snapshot contains.
- Good commit messages are short and clear.

### Step 5: Name your main branch (if needed)

```bash
git branch -M main
```

### Step 6: Connect your local repo to GitHub

```bash
git remote add origin https://github.com/your-username/python-course.git
```

- This links your local project to the online repository, naming the remote `origin`.
- Use the URL shown on your GitHub repository page.

### Step 7: Push your code

```bash
git push -u origin main
```

- This uploads your commits to GitHub.
- `-u` sets the default upstream, so later you can simply use `git push`.
- GitHub may ask you to sign in or authenticate the first time (for example, through a browser window or a personal access token, since GitHub no longer accepts account passwords for Git operations over HTTPS).

### Step 8: Verify

Refresh your repository page on GitHub. You should see `hello.py` listed there.

### The workflow in one picture

```
Edit code → git add → git commit → git push
(working folder) → (staging) → (local history) → (GitHub)
```

### Using VS Code's built-in Source Control (alternative)

VS Code can do these steps with buttons:

1. Click the **Source Control** icon in the left sidebar.
2. Click **Initialize Repository** (or open an existing repo).
3. Enter a commit message and click **Commit**.
4. Click **Publish Branch** / **Sync Changes** to push to GitHub.

The buttons run the same Git commands behind the scenes.

---

## 11. Common Problems and Fixes

| Problem | Likely Cause | Fix |
|---|---|---|
| `python is not recognized...` (Windows) | Python not added to PATH | Reinstall Python and tick **Add python.exe to PATH**, or add it to PATH manually |
| `command not found: python` (macOS/Linux) | The command is named differently | Try `python3` instead |
| `NameError: name 'Print' is not defined` | Wrong capitalization | Use lowercase `print` |
| `SyntaxError` | Missing quote or bracket | Check that every `"` and `(` has a matching closing one |
| `can't open file 'hello.py'` | Terminal is in the wrong folder, or the file name is wrong | Check the folder with `cd`, and confirm the file name and `.py` extension |
| No output appears | File not saved, or code not run | Save with `Ctrl + S` and run again |
| `git is not recognized` | Git not installed | Install Git from git-scm.com and restart the terminal |
| `git push` rejected or authentication fails | Not logged in, or wrong remote URL | Re-authenticate and confirm the remote with `git remote -v` |

---

## 12. Quick Revision

- **VS Code** is a free code editor by Microsoft; download it from **code.visualstudio.com**.
- **Python** must be installed separately from **python.org**. On Windows, always tick **Add python.exe to PATH**.
- Check the installation with `python --version` (or `python3 --version`).
- Install the **Python extension** (by Microsoft) in VS Code.
- Python files use the **`.py`** extension.
- The first program: `print("Hello, World!")`.
- Run it from the terminal with `python hello.py`, or use the **Run** button.
- `print()` is a function; text inside quotes is a **string**; Python is **case-sensitive**.
- **Git** tracks changes locally; **GitHub** hosts repositories online.
- Key terms: **repository, commit, push, pull, clone, branch, remote**.
- Basic workflow: `git init` → `git add .` → `git commit -m "message"` → `git remote add origin <URL>` → `git push -u origin main`.

---

## 13. Self-Check

1. Why do we need to install both VS Code and Python? Can one replace the other?
2. Where should you download Python and VS Code from?
3. What does the "Add python.exe to PATH" option do, and why is it important?
4. Which command checks your Python version?
5. What does each part of `print("Hello, World!")` mean?
6. What is the difference between Git and GitHub?
7. What do `git add`, `git commit`, and `git push` each do?
8. How would you fix the error "python is not recognized as an internal or external command"?