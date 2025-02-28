### **Vim Basics Cheat Sheet** 📝  

Vim (Vi IMproved) is a powerful text editor used in Linux and programming environments. Here’s a **quick guide** to help you get started.
```bash
vimtutor
# to learn about vim by vim itself
```  
---

## **🔹 Opening & Exiting Vim**
| Command | Description |
|---------|------------|
| `vim filename` | Open a file (or create a new one if it doesn’t exist) |
| `:w` | Save the file (write changes) |
| `:q` | Quit Vim |
| `:wq` or `ZZ` | Save and quit |
| `:q!` | Quit without saving |

---

## **🔹 Vim Modes**
| Mode | Description |
|------|------------|
| **Normal Mode** | Default mode (used for navigation & commands) |
| **Insert Mode** | For typing text (`i`, `a`, `o` to enter) |
| **Visual Mode** | For selecting text (`v`, `V`, `Ctrl+v`) |
| **Command Mode** | For executing commands (`:` to enter) |

---

## **🔹 Switching Modes**
| Key | Mode Switch |
|-----|------------|
| `Esc` | Return to **Normal Mode** |
| `i` | Insert before the cursor (**Insert Mode**) |
| `a` | Insert after the cursor (**Insert Mode**) |
| `o` | Insert a new line below (**Insert Mode**) |
| `v` | Start visual selection (**Visual Mode**) |
| `V` | Select full lines (**Visual Line Mode**) |
| `Ctrl+v` | Select block-wise (**Visual Block Mode**) |

---

## **🔹 Navigation**
| Command | Movement |
|---------|---------|
| `h` | Left |
| `l` | Right |
| `j` | Down |
| `k` | Up |
| `0` or `^` | Start of the line |
| `$` | End of the line |
| `gg` | Go to beginning of file |
| `G` | Go to end of file |
| `Ctrl+d` | Move half-page down |
| `Ctrl+u` | Move half-page up |

---

## **🔹 Editing & Deleting**
| Command | Action |
|---------|--------|
| `x` | Delete character under cursor |
| `dd` | Delete (cut) the current line |
| `yy` | Copy (yank) the current line |
| `p` | Paste after cursor |
| `P` | Paste before cursor |
| `u` | Undo |
| `Ctrl+r` | Redo |

---

## **🔹 Searching & Replacing**
| Command | Action |
|---------|--------|
| `/word` | Search forward for "word" |
| `?word` | Search backward for "word" |
| `n` | Repeat last search forward |
| `N` | Repeat last search backward |
| `:s/old/new/g` | Replace "old" with "new" in the current line |
| `:%s/old/new/g` | Replace in the whole file |

---

## **🔹 Working with Multiple Files**
| Command | Action |
|---------|--------|
| `:e filename` | Open another file |
| `:bn` | Next buffer (file) |
| `:bp` | Previous buffer (file) |
| `:bd` | Close buffer |
| `:split filename` | Split window horizontally |
| `:vsplit filename` | Split window vertically |
| `Ctrl+w` + `arrow` | Switch between splits |

---
