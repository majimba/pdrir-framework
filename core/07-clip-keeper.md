# 07. Follow-Along Project: Clip-Keeper

[Back to Home](../index.md)

## Project Introduction

Let's apply this entire framework to build the clipboard manager we've been deconstructing.

Project: 'Clip-Keeper'

## Applying PDRIR Step-by-Step

### Phase 1: Problem

Problem Statement: "As a user who frequently reuses text snippets (links, commands, email responses), I need a way to quickly save and retrieve items from my clipboard history without a messy text file, so I can work more efficiently."

MVP Criteria:

- Save current clipboard content with a global hotkey (Ctrl+Alt+C).
- Display saved clips in a simple GUI, activated by another hotkey (Ctrl+Alt+V).
- Clicking a clip in the GUI copies it back to the clipboard and closes the GUI.

### Phase 2: Deconstruction

(As detailed in earlier chapters, we have 8 fundamental truths to solve.)

### Phase 3: Research

Libraries Chosen:

- pynput for global hotkey listening.
- pyperclip for clipboard access.
- tkinter for the GUI.
- json for saving the data to a file.

Prototypes: Create test_pynput.py, test_pyperclip.py, and test_tkinter.py to validate each part works in isolation.

### Phase 4: Implementation (The Code)

Create a clip_keeper.py file. The final code would look conceptually like this (simplified):

```python
# clip_keeper.py - A simple clipboard manager
import tkinter as tk
from pynput import keyboard
import pyperclip
import json
import sys

# --- 1. MODEL: Data Storage & Logic ---
SAVED_DATA_PATH = "clipboard_history.json"
clipboard_history = []

def load_data():
    global clipboard_history
    try:
        with open(SAVED_DATA_PATH, 'r') as f:
            clipboard_history = json.load(f)
    except FileNotFoundError:
        clipboard_history = [] # Start fresh if no file

def save_data():
    with open(SAVED_DATA_PATH, 'w') as f:
        json.dump(clipboard_history, f)

def add_current_clipboard():
    content = pyperclip.paste()
    if content and content not in clipboard_history:
        clipboard_history.insert(0, content) # Add to the top
        save_data()
        print("Saved to clipboard history.")

# --- 2. VIEW: The User Interface (Tkinter) ---
app_window = None

def show_ui():
    global app_window
    if app_window:
        app_window.destroy() # Close old window if it exists

    app_window = tk.Tk()
    app_window.title("Clip-Keeper")
    app_window.attributes("-topmost", True) # Keep window on top

    # Add items to a listbox
    listbox = tk.Listbox(app_window)
    for item in clipboard_history:
        # Show a truncated version for readability
        display_text = (item[:75] + '...') if len(item) > 75 else item
        listbox.insert(tk.END, display_text.strip())
    listbox.pack(padx=10, pady=10, fill=tk.BOTH, expand=True)

    def on_select(event):
        # Get selected original text from the main list
        selected_indices = listbox.curselection()
        if selected_indices:
            original_text = clipboard_history[selected_indices[0]]
            pyperclip.copy(original_text)
            app_window.destroy() # Close on selection

    listbox.bind("<<ListboxSelect>>", on_select)
    app_window.mainloop()

# --- 3. CONTROLLER: Hotkey Listener (pynput) ---
def on_press(key):
    # This function runs in the background
    pass # We use on_activate for hotkeys

def for_canonical(f):
    # Hotkey helper
    return lambda k: f(listener.canonical(k))

# Define hotkey actions
hotkey_actions = {
    '<ctrl>+<alt>+c': add_current_clipboard,
    '<ctrl>+<alt>+v': show_ui,
}

# Create the listener
# The listener runs in a separate thread
print("Clip-Keeper is running in the background.")
print("Press Ctrl+Alt+C to save clipboard.")
print("Press Ctrl+Alt+V to view history.")

load_data() # Load history on startup
with keyboard.GlobalHotKeys(hotkey_actions) as listener:
    listener.join()
```

### Phase 5: Refinement

Problem: The UI is basic. I want to be able to search my clips.

New PDRIR cycle:

- P(roblem): Can't find old clips easily.
- D(econstruct): Need an input box in the UI. Need to filter the displayed list based on the input box text.
- R(esearch): "tkinter entry widget", "tkinter filter listbox".
- I(mplement): Add the tk.Entry widget and a function that runs on keypress to rebuild the listbox content.
- R(efine): Search should be case-insensitive. Use .lower() on both the search term and the clip content.

---

Prev: [06. Phase 5: Refinement](./06-phase-5-refinement.md) | Next: [08. Framework Validation](./08-framework-validation.md) | [Back to Home](../index.md)
