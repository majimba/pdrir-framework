# 05. Phase 4: Implementation (The 'Do')

[Back to Home](../index.md)

Core Principle: Assemble the prototyped solutions into a single, functioning system that meets the MVP criteria.

This is the assembly phase. You're moving from scientist to engineer.

## Process

- Create the Main Project File: clip_keeper.py.
- Structure with Comments: Copy your "Truths" from Phase 2 into your main file as comments. This forms the skeleton of your application.
- Integrate Prototypes: Bring in the code from your test_*.py files into the relevant sections.
- Connect the System: This is the most challenging part. It's where you apply [Systems Thinking](../guides/systems_thinking.md). How does the data flow?
  - The pynput hotkey listener (Truth 1) needs to call a function.
  - That function will use pyperclip to get the data (Truth 3).
  - That data is then added to a list, which is your data model (Truth 4).
  - The tkinter GUI will read from that same list to display the items (Truth 5).
  - A button in the tkinter GUI will trigger a function that takes an item and uses pyperclip to write it back to the clipboard (Truth 8).
- Focus on "Working," Not "Perfect": Do not add features. Do not worry about edge cases. Just make it meet the three MVP success criteria. Does it save? Does it display? Does it copy back? If yes, you are done with this phase.

## Output

A single script, clip_keeper.py, that successfully functions as a Minimum Viable Product.

---

Prev: [04. Phase 3: Research](./04-phase-3-research.md) | Next: [06. Phase 5: Refinement](./06-phase-5-refinement.md) | [Back to Home](../index.md)
