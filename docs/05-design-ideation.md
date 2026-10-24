
from pathlib import Path
import tkinter as tk
from tkinter import filedialog

root = tk.Tk()
root.withdraw()

file_path = filedialog.askopenfilename(
    title="Select your cleaned Ideation Markdown file",
    filetypes=[("Markdown files", "*.md")]
)

if file_path:
    markdown = Path(file_path).read_text(encoding="utf-8")

    root.clipboard_clear()
    root.clipboard_append(markdown)
    root.update()

    print("Your complete Ideation page is copied!")
    print("Open GitHub and press Ctrl + V to paste it.")
else:
    print("No file selected.")

root.destroy()
