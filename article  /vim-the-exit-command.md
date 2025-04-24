# Vim : The Exit Command

`Date: 30 March 2025`

![Picsart_25-03-30_17-02-13-838](https://github.com/user-attachments/assets/89be7c0c-c2c1-4b4c-96fc-02a9db7ed9a4)

Vim is a powerful command-line editor designed to boost your coding speed—even if you're using it to write another editor within Vim itself.

This article will take you from struggling to exit Vim to customizing your own keybindings for quitting like a pro.

## Table of Content

- [Modes](#modes)
  - [Normal Mode](#normal-mode)
    - [Cursor Movement](#cursor-movement)
    - [Movement with Numbers](#movement-with-numbers)
    - [Undo & Redo](#undo--redo)
    - [Searching](#searching)
    - [Marking Points](#marking-points)
    - [Other Useful Commands](#other-useful-commands)
  - [Insert Mode](#insert-mode)
  - [Command Mode](#command-mode)
  - [Configuration](#configuration)
  - [Visual Mode](#visual-mode)
    - [Combining with Numbers](#combining-with-numbers)
    - [Change & Replace](#change--replace)
    - [Word and Line Navigation](#word-and-line-navigation)
    - [Deleting Words](#deleting-words)
    - [Line Navigation](#line-navigation)
    - [File Navigation](#file-navigation)
    - [Indentation & Repetition](#indentation--repetition)
  - [Visual Line Mode](#visual-line-mode)
  - [Visual Block Mode](#visual-block-mode)
  - [Registers & Macros](#registers--macros)
    - [Registers](#registers)
    - [Macros](#macros)



## Modes

### Normal Mode

#### Cursor Movement

- `h` : Move left  
- `l` : Move right  
- `j` : Move down  
- `k` : Move up  

#### Movement with Numbers

- `{number}h`, `{number}l` → Move left/right `{number}` times (e.g., `4h` moves 4 characters left)
- `{number}j`, `{number}k` → Move down/up `{number}` lines (e.g., `4j` moves 4 lines down)

#### Undo & Redo

- `u` : Undo
- `Ctrl + r` : Redo
- `{number}u` : Undo `{number}` times (e.g., `3u` undoes 3 times)
- `{number}Ctrl + r` : Redo `{number}` times

#### Searching

- `/X` : Search for `X`, press `n` to jump to the next occurrence, `Shift + n` to go back
- `*` : Search forward for the word under the cursor
- `#` : Search backward for the word under the cursor

#### Marking Points

- `mX` : Mark the current position with `X` (where `X` is any character)
- `'X` : Jump to the marked position

#### Other Useful Commands

- `zz` : Center the current line in the window

### Insert Mode

- `a` : Insert after the character  
- `i` : Insert before the character  
- `o` : Insert on a new line below the current line  
- `Shift + a` : Insert at the end of the line  
- `Shift + i` : Insert at the beginning of the line  
- `Shift + o` : Insert on a new line above the current line  

### Command Mode

- Press `:` and enter the command (e.g., `:set number` to enable line numbers)
- `:set relativenumber` : Show relative line numbers
- `:set mouse=a` : Enable mouse support
- `:%s/X/Y/g` : Replace all occurrences of `X` with `Y` in the entire file
- To replace within a selected area in Visual Mode:  
  `:s/X/Y/g`

### Configuration

- Location: `~/.vimrc`

We can place any settings in `~/.vimrc` to make them permanent.

```
set mouse=a
set number
set relativenumber
```

### Visual Mode

- Press `v` to enter Visual Mode
- `d` : Delete selection
- `dd` : Delete the entire line
- `Shift + d` : Delete from cursor to end of the line
- `y` : Copy (Yank in Vim)
- `yy` : Yank the whole line
- `p` : Paste after cursor
- `Shift + p` : Paste before cursor

##### Combining with Numbers

- `{number}p` : Paste `{number}` times
- `{number}d` : Delete `{number}` lines

##### Change & Replace

- `c` : Delete and enter Insert Mode
- `cc` : Change the entire line (delete and enter Insert Mode)
- `Shift + c` : Delete from cursor to the end of the line and enter Insert Mode
- `rX` : Replace the character under the cursor with `X`

##### Word and Line Navigation

- `w` : Jump forward by one word
- `Shift + w` : Jump forward treating consecutive characters as a single word
- `e` : Jump to the end of the word
- `b` : Jump backward by one word

##### Deleting Words

- `dw` : Delete one word
- `d{number}w` : Delete `{number}` words (e.g., `d2w` deletes two words)
- `diw` : Delete the word under the cursor

##### Line Navigation

- `0` : Move to the beginning of the line
- `$` : Move to the end of the line
- `ciX` : Change the content inside an enclosure (e.g., `ci"` to change inside `" "`)
- `%` : Jump between matching brackets (`{}`, `[]`, `()`)
- `tX` : Jump just before the next occurrence of `X`
- `fX` : Jump directly to `X`
- `Shift + tX` : Jump before `X`

##### File Navigation

- `gg` : Jump to the beginning of the file
- `Shift + g` : Jump to the end of the file
- `{number}Shift + g` : Jump to line `{number}`

##### Indentation & Repetition

- `=` : Auto-indent
- `.` : Repeat the last command

### Visual Line Mode

- `Shift + v` : Select entire lines

### Visual Block Mode

- `Ctrl + v` : Select a block of text

### Registers & Macros

#### Registers

- `:reg` : Show all registers
- Use `"<register><command>` (e.g., `"ap` pastes from register `a`)

#### Macros

- `qX` : Start recording macro in register `X`
- `q` : Stop recording
- `@X` : Execute macro stored in register `X`
- Macros can be nested by calling other macros inside them
