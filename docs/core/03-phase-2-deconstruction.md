# 03. Phase 2: Deconstruction (The 'What')

[Back to Home](../index.md)

Core Principle: Break the problem into its fundamental, verifiable truths.

This is where you apply [First-Principles Thinking](../guides/first_principles_thinking.md). You are not allowed to think about specific libraries or existing solutions. You must think about the essential truths of your MVP definition.

## Process

## The Critical Difference: Truths vs. Tasks

This is the most common failure point in the Deconstruction phase. We instinctively jump to solutions ("Tasks") instead of defining the underlying problem ("Truths"). Focusing on Truths keeps your options open and prevents you from building the wrong thing.

A **Task** is *how* you might solve something. A **Truth** is *what* must be solved.

Here is a clear example based on our Clip-Keeper project:

| Common Mistake (A Task) | Better Approach (A Truth) | Why It's Better |
| :--- | :--- | :--- |
| "Build a UI with Tkinter." | "The user must be able to **see** a list of their saved clips." | This Truth allows for other solutions (a web page, a console app, a native UI) if Tkinter proves difficult. |
| "Listen for a global hotkey."| "The program must be able to **react** to user input even when it's not the active window." | This focuses on the core problem. The solution could be hotkeys, a menu bar icon, or a system service. |
| "Save the clips to a JSON file."| "The program needs a way to **persist** data between restarts." | This Truth opens up other storage options like a database, a CSV file, or cloud storage, depending on future needs. |

Always ask: "Am I describing a specific tool or action, or am I describing a fundamental requirement?"

Let's deconstruct our clipboard manager's MVP using first principles.

### MVP Goal 1: "Press a hotkey to save whatever is currently on my clipboard."

- Truth 1: The program must be able to run constantly in the background, listening for keyboard input without being the active window.
- Truth 2: It must be able to detect a specific key combination (a "hotkey").
- Truth 3: When the hotkey is detected, the program must be able to access the computer's clipboard and read its current content.
- Truth 4: The program needs a place to store the content it reads. A list in memory or a simple file would be the most fundamental storage.

### MVP Goal 2: "See a list of all saved items."

- Truth 5: The program needs a user interface (UI) to display the stored items. The most fundamental UI is text printed in the console. A slightly more advanced one is a simple graphical window.
- Truth 6: The UI must be able to be opened, perhaps by clicking an icon or using another hotkey.

### MVP Goal 3: "Click an item from the list to copy it back to my clipboard."

- Truth 7: The UI must be interactive. The user needs to be able to select a specific item from the list.
- Truth 8: Upon selection, the program must be able to write the content of the selected item back to the computer's clipboard.

## Output

A numbered list of the fundamental technical challenges you need to solve. You have transformed one large problem into eight smaller, distinct, and highly searchable mini-problems.

