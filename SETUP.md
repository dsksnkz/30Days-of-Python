# Setup

Pick your system and follow its steps, then go to **Your first program** below.

## Windows

1. Install Python. Either:
   - download the installer from [python.org/downloads](https://www.python.org/downloads/). On the first screen, **tick "Add python.exe to PATH"** before you click Install, or
   - open **Terminal** (or PowerShell) and run: `winget install Python.Python.3.13`
2. **Close and reopen Terminal**, then check that it worked:
   ```powershell
   python --version
   ```
3. If typing `python` opens the Microsoft Store instead, either install from python.org as above, or use `py` instead of `python` everywhere in this course. `py` is the Python launcher, and it comes with the python.org installer.

## macOS

```bash
brew install python      # needs Homebrew: https://brew.sh
python3 --version
```

Or use the installer from [python.org/downloads](https://www.python.org/downloads/). On macOS, type `python3` wherever the course says `python`.

## Linux

Most distributions already have Python. Check with `python3 --version`. If it's missing:

| Distribution | Command |
|---|---|
| Ubuntu, Debian, Mint | `sudo apt install python3 python3-pip python3-venv` |
| Fedora | `sudo dnf install python3` |
| Arch | `sudo pacman -S python python-pip` |

On some distributions `python` doesn't exist and only `python3` does. Use whichever works.

You need **Python 3.12 or newer**.

## Pick an editor

**VS Code** works on every system. Get it from [code.visualstudio.com](https://code.visualstudio.com/), then install the **Python** extension. Any editor is fine, though. Notepad++, Neovim, PyCharm and IDLE (which comes with Python) all work.

Set your editor to use **4 spaces** for indenting. In Python, indenting isn't just tidiness: it's part of the code.

## Your first program

Make a folder, put a file in it, and run it. These commands work in PowerShell, macOS Terminal and Linux shells:

```bash
mkdir Day01
cd Day01
```

Create `hello.py` in that folder with your editor, containing:

```python
print("Hello, Python")
```

Then run it:

```bash
python hello.py
```

## The REPL

Type `python` with no file to get a `>>>` prompt. It runs each line as soon as you press Enter, which is great for testing a small idea:

```
>>> 7 / 2
3.5
>>> len("hello")
5
```

Leave with `exit()`.

## Installing packages (from Week 3)

Give each project its own **virtual environment**, so packages don't clash. Some Linux distributions even block `pip install` outside one, with `error: externally-managed-environment`.

Create it once per project:

```bash
python -m venv .venv
```

Then turn it on each time you open a terminal:

| System | Command |
|---|---|
| Windows (PowerShell) | `.venv\Scripts\Activate.ps1` |
| Windows (cmd) | `.venv\Scripts\activate.bat` |
| macOS and Linux | `source .venv/bin/activate` |

You'll see `(.venv)` at the start of the prompt. Now `pip install requests` installs into this project only. Type `deactivate` when you're done.

If PowerShell says **running scripts is disabled on this system**, run this once, then try again:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

## Git (for saving your work)

- **Windows:** `winget install Git.Git`, or download from [git-scm.com](https://git-scm.com/).
- **macOS:** `xcode-select --install`, or `brew install git`.
- **Linux:** install `git` with your package manager.
