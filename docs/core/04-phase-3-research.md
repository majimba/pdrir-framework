# 04. Phase 3: Research (The 'How')

[Back to Home](../index.md)

Core Principle: Find the tools to solve each deconstructed truth, one at a time.

Armed with your list from Phase 2, you can now perform surgical, targeted research. You are no longer "looking for ideas"; you are "looking for tools."

## Process

For each "truth" from Phase 2, find the library or technique to achieve it.

- Truth 1 & 2 (Background listener, hotkey):
  - Search Query: "python run in background listen for keyboard" -> Libraries like pynput or keyboard.
- Truth 3 & 8 (Access clipboard):
  - Search Query: "python copy and paste clipboard" -> Libraries like pyperclip.
- Truth 4 (Storage):
  - Search Query: "python save list to file" -> Concepts like JSON files or simple text files.
- Truth 5, 6, 7 (GUI):
  - Search Query: "python simple graphical user interface" -> Standard libraries like tkinter or third-party options like PySimpleGUI.

## Prototyping sub-step

Create a tiny prototype for each mini-problem.

- test_hotkey.py: Print "Hello!" when pressing Ctrl+Shift+C.
- test_clipboard.py: Print whatever is on the clipboard.
- test_gui.py: Display a window with a list of dummy items.

This isolates each problem and confirms you can solve it before you try to connect them ([Systems Thinking](../guides/systems_thinking.md)).

## Output

A set of small, working prototype scripts, one for each core challenge, and a list of the libraries you will use.

