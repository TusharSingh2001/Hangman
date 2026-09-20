# Hangman

A terminal-based hangman game written in Python. The computer picks a secret
word, you guess one letter at a time, and you lose a life for every letter that
isn't in the word. Reveal the whole word before your lives run out and you win.

## Prerequisites

Python 3. Nothing else — the game uses only the Python standard library, so
there is nothing to install.

macOS and most Linux systems already have Python 3. On Windows you may need to
install it from [python.org](https://www.python.org/downloads/).

To check what you have, open a terminal and run:

```
python3 --version
```

Any version starting with `3.` will work.

## Getting the code

Either download it or clone it — both give you the same files.

**Download (no tools needed):** click the green **Code** button at the top of
this page, choose **Download ZIP**, then unzip it.

**Clone (requires Git):**

```
git clone https://github.com/TusharSingh2001/Hangman.git
```

## How to run the game

### macOS

Open Terminal, move into the project folder, then start the game:

```
cd ~/Downloads/Hangman-main
python3 hangman.py
```

Adjust the first line if you put the folder somewhere other than Downloads, or
if it unzipped under a different name. A shortcut that avoids typing the path
at all: right-click the project folder in Finder, then choose
**Services → New Terminal at Folder**. The terminal opens already inside it, so
you can skip straight to `python3 hangman.py`.

The command is `python3`, not `python`. macOS no longer ships a `python`
command, so plain `python` gives you `command not found`.

The first time you run it, macOS may offer to install the command line
developer tools. Click **Install**, wait for it to finish, then run the command
again.

### Windows

Open Command Prompt or PowerShell:

```
cd %USERPROFILE%\Downloads\Hangman-main
py hangman.py
```

Use `py` on Windows. If that isn't recognised, try `python hangman.py`.

A shortcut: open the project folder in File Explorer, click the address bar,
type `cmd`, and press Enter. The terminal opens in that folder.

### Linux

```
cd ~/Downloads/Hangman-main
python3 hangman.py
```

## Run it from the project folder

The game reads its word list from `words.json`, and it looks for that file in
whatever folder your terminal is currently in — not the folder the script lives
in. If you run the script from somewhere else, you'll get:

```
FileNotFoundError: words.json
```

The fix is to `cd` into the project folder first. To confirm where you are, run
`pwd` on macOS or Linux, or `cd` on its own in Windows Command Prompt.

## How to play

The game shows the secret word as underscores, one per letter:

```
_ _ _ _ _
```

Type a single letter and press Enter. Correct guesses fill in every place that
letter appears. Wrong guesses cost you a life. Keep going until you either
complete the word or run out of lives.

A reasonable opening strategy is to try the common letters first — E, A, R, S,
T, N — and use the revealed pattern to work out the rest.

## Adding your own words

The word list lives in `words.json`, kept separate from the code so you can
extend it without touching any Python. Open it in any text editor and add
entries to the list, keeping the existing formatting:

```json
["python", "keyboard", "mountain", "your-new-word"]
```

Save the file and run the game again to pick up the change.

## Troubleshooting

| What you see | What it means | Fix |
| --- | --- | --- |
| `zsh: command not found: python` | macOS has no `python` command | Use `python3 hangman.py` |
| `'py' is not recognized` | Python isn't installed or isn't on PATH | Install from python.org and tick "Add Python to PATH" |
| `FileNotFoundError: words.json` | You're in the wrong folder | `cd` into the project folder first |
| `cd: no such file or directory` | The path doesn't exist | Check the folder name — a downloaded ZIP often unzips as `Hangman-main` |
| `SyntaxError` on startup | Running under Python 2 | Use `python3` explicitly |

## Project structure

```
hangman.py    the game logic
words.json    the list of words the game chooses from
README.md     this file
```

