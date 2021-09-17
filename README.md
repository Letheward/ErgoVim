# ErgoVim

> If you use UK style or DVORAK keyboard, or something like HHKB,  
> ErgoVim may not work as intented.  
> 
> This README assume you use **STANDARD US style** keyboard.

## Introduction

ErgoVim is a ergonomic keymapping for Vim.  
Design for comfort, intuition and efficiency.

Also, ErgoVim is minimal and easy to reason about,  
so you can customize/extend it to your needs with low friction.

## How to Install

- Vimer that already have a setup:
    
    0. ErgoVim breaks **EVERYTHING** from classic Vim.  
    **DON'T** directly copy this vimrc to your vim config or plugin folder.  
    **BACKUP** your setup first.  

    1. Download from [release](https://github.com/Letheward/ErgoVim/releases) or clone this repository.
    
    2. Read the `vimrc` source code, cheatsheet and "How to Use" in this README carefully.

    3. Figure out how to integrate the keymap to your own setup.
 
- Using Neovim with no setup:

    1. Open Neovim, type `:echo stdpath('config')` and Enter. 
    It will output something like this: `C:\Users\You\AppData\Local\nvim`. (this is on windows)
    
    2. Go to that folder, if there is none, create a `nvim` folder.
    
    3. Close Neovim by typing `:qa!` and Enter.

    4. Download from [release](https://github.com/Letheward/ErgoVim/releases) or clone this repository.

    5. Rename ErgoVim's `vimrc` to `init.vim`.
    
    6. Put `init.vim` to the folder in step 1. 

    7. Open Neovim again, you may notice something has changed.  
    Hit \` key, type `qa!` and Enter to exit.

- Using vanilla Vim with no setup:

    1. Open Vim and type `:version`, hit `Enter`. It will output something like this:  
    (you may need to hit `Enter` to scroll down to see all of it.)

        ~~~
        :version
        VIM - Vi IMproved ...
        Compiled by ...
        ...  Features included (+) or not (-):
        ...

        system vimrc file: "/etc/vimrc"
            user vimrc file: "$HOME/.vimrc"
        2nd user vimrc file: "~/.vim/vimrc"
            user exrc file: "$HOME/.exrc"
            defaults file: "$VIMRUNTIME/defaults.vim"
        fall-back for $VIM: "/etc"
        f-b for $VIMRUNTIME: "/usr/share/vim/vim82"
        Compilation: ...
        ~~~

    2. Go to these directories:
        - `system vimrc file`
        - `user vimrc file`
        - `2nd user vimrc file`

        If you are using MinGW, they might endup being in your MinGW distro's `/etc/`, etc.  

    3. **BACKUP** existing `vimrc` files. (they may be hidden in file explorer)  

    4. Download from [release](https://github.com/Letheward/ErgoVim/releases) or clone this repository.

    5. Choose one from these 3 directories to install ErgoVim. Base on what directory you choose, you may have to rename ErgoVim's `vimrc`. 

        - If you are using MinGW on Windows, `system vimrc file` is recommended.
        - If you don't know how to delete files in protected `/etc/`,  
        you can choose `user vimrc file` (but system `vimrc` will still be there and functioning).
        - If you want to install to `2nd user vimrc file`,  
        you may need to create a `.vim` folder if there is none.
    
    6. Put ErgoVim's `vimrc` to your chosen directory (will **overwrite** existing `vimrc`) 

    7. Open Vim again, you may notice something has changed.  
        Hit \` key, and type `qa!`, and Enter to exit.  

    999999999. After you are familiar with Vim, look into the older `vimrc` files you've backed up.  
    Get features you want back to you config.

## How to Use

![cheatsheet](img/Cheatsheet.png)
(the cheatsheet, right-click/long-press to download if text is too small on your device)  
(also there is a copy in the zip folder download from [release](https://github.com/Letheward/ErgoVim/releases))

### A Basic Walk-through

- Part I
1. Open Vim. Naturally rest your left hand on `wasd`, right hand on `ijkl`.
1. Hit `ll` to enter **Insert Mode**.
1. Enter some gibberish, need to have spaces and blanklines, and long enough that you need to scroll the screen.
1. Hit `Esc` to back to **Normal Mode**.
1. `w`, `a`, `s`, `d` to move cursor.
1. `q`, `e`, `r`, `f` to move by word and paragraph.
1. `W`, `S` (capital means with `Shift`) to scroll pages.
1. `A`, `D` to go to soft line beginning and end (soft means it will ignore spaces at start or end of line).
1. `Ctrl-a` and `Ctrl-d` to go to hard line beginning and end.
1. `Ctrl-w` and `Ctrl-s` to go to file beginning and end.

- Part II
1. `k` to backspace, `K` to delete.
1. `u` to undo, `U` to redo.
1. `m` to enter **Visual Mode** (this is just selecting) and back. Using `Esc` also goes back to **Normal Mode**.
1. Using all the movement keys in Part I to change selection range in **Visual Mode**.
1. In **Visual Mode**, `j` to cut selection, `i` to copy selection.
1. In **Normal Mode**, `jj` to cut a line, `ii` to copy a line. 
1. In **Normal Mode**, `o` to paste after cursor or line, `O` to paste before cursor or line. 
1. In **Visual Mode**, `Ctrl-x`, `Ctrl-c` to cut, copy to system clipboard. 
1. In **Normal Mode**, `Ctrl-v` to paste from system clipboard.

- Part III
1. Hit \` Key to enter Command Line Mode.
1. Type `help cmdline` and hit `Enter`.
1. `xid` to open a copy of that window to the right.
1. `xx` to change window.
1. `xs` to go to window below.
1. `xk` to close current window.
1. `xl` to make current window fullscreen.

### Semantics:

- Direction Keys:

    - `ld` is insert to the *right* of this line.
    - `jf` is cut *down the block*.
    - `ie` is copy until the *word right*.

- Action Keys:

    - (same as leader, like `jj`, `ii`, `xx`) do the basic stuff
    - `l` enter, confirm, do things
    - `k` cancel, delete, exit, close
    - `j` change, cut, join
    - `i` copy, identity
    - `n` new

Examples:

- `xna`: open a *window* to edit *new file*, to the *left*.  
- `Zl`: *entering* the fold.  
- `nk`: *cancel* search highlight.   
- `ni`: *search* using the word under *current* cursor location. 

### Basic Editing

(TODO)

### Key Sequences

(TODO)

### Window Management

(TODO)

### Advance Editing

(TODO)

### Tips

- Don't try to memorize/utilize everything at once. Get the basic stuff done first, then gradually build up your muscle memory.

- Use large motions for fast move.

- Avoid using your pinky as possible:

    ErgoVim tries to minimize pinky usage, however inevitably there are features needing `Shift` and `Ctrl`.  
    In those cases, since those features are less frequent by design, you should use your stronger fingers/both hands, without worrying about speed loss for moving your hands out of homerow.

    Also, if you need to hit `Tab` repeatly (like auto-completion in `cd`), you should use a stronger finger (or even multiple fingers) to do that.

### Customize

Some Examples:

- Even simpler ErgoVim:
    - map `l` to insert mode, and delete every `l` leading sequence
    - change `n` to `/` and delete every `n` leading sequence
    - map `j` to `dd` and `i` to `yy`, and delete every `j`, `i` leading sequence, edit using visual mode only.

- Adding new functionality:
    1. add some `fooBarWindowManager` plugin
    2. find out it's a plugin about windows, so using leading key `x`
    3. find the function `fooBarFunction()`
    4. map `xh` to `:fooBarFunction()<Return>`

## How to Contribute

### Help testing on other platforms

You can test on Mac OS, Linux, or any UNIX, also on gVim, NeoVim and other Vim forks.

Please report every bug or weird behavior you find.

### Adding New Features

Make sure you understand the design philosophy.

Heavy scripting is not recommended.

Breaking Changes are welcome if they are beneficial.

### Editing Cheatsheet SVG

You need to Install Inkscape, font `JetBrains Mono` and `Ubuntu Condensed`.

Palette used is the included `Android icon palette`.

Keep it clean and legible.

If you want to output png, `48DPI` or half the size is recommended,  
small size yet also legible. (smallest font in half size is equal to 16px)

If you want to output svg for users, make sure to convert all text to path.  
(it's recommended to convert text by part because it's slow and may freeze Inkscape)

## Q&A

- > Vim is already ergonomic.

    We may have very different understandings of the word "ergonomic".

- > My favorite Vim features are missing.

    You can try to translate them to the style of new design, and check if there is room in key sequence namespaces for them.

- > I am left handed/used to right hand on Arrows/have only one hand.

    ErgoVim will be nonetheless a new mapping for you, so you can choose to learn it the original way.  

    Or, understand ErgoVim's philosophy and remap everything yourself, this should be easy to reason about, but tedious to do (just like developing ErgoVim against classic Vim).  
    In the end, if that makes you use Vim better, it's worth it, because software should adjust to people, not the other way around.

- > Why don't you remap `Esc` with something like `jk` or `jj`?

    Because sometimes you do need to write `jk` or `jj`, and when you type `j` you will think not type `k`, which slows you down and will mess up your flow.

    Change `jk` to anything else uncommon that you can type as text won't work either.  
    The Proof: How do you write your keymap manual using Vim with your new `Esc` remap?

- > How about `Alt` and `CapsLock` ?

    These Keys don't work consistently across multiple OS/Terminals.  
    Typical `CapsLock` / `Esc` / `Ctrl` swap is done by registry hack/OS config/AHK, etc.

    If you know how to fix the problem by vimscript only,  and get it work on every major platform, please do a PR or write a issue.

## Known Issues

This `vimrc` file is already tested on:
- Vim 8.2 (huge version), MinTTY/MinGW, Windows 10. (developed on)
- Vim 8.1 (huge version), Konsole/X11/KDE Plasma 5.21.5, KDE Neon 5.21. (no problem found yet)
- Vim 8.2 (small version), GNOME Terminal/Wayland/GNOME 3.38.1, Fedora 33. (partially working)
- Neovim v0.5.0, nvim-qt, Windows 10. (minor issues)
- VS Code Vim (yes, they have experimental `vimrc` support). (partially working)

Issues:
- `CapsLock` will change commands to uppercase commands on the same key.
- Some Commands will behave like the old way if it's hold other than tapped.
- Search back `n` will perform once more if hold (due to how it's designed), wait for it or hit `N` to cancel.
- Default small version Vim miss many features, like text object, auto-complete, etc.   
    Using key sequences for those features may cause unwanted behavior.
- `Shift-Enter` on GNOME Terminal/Fedora 33 is not working.
- Terminal window switching is not ideal.
- On Neovim, Visual mode cursor `a` and `d` may need extra key inputs to function.
- Terminal on Neovim is not working as expected.

## License

The `vimrc` file is dedicated to public domain, or under [CC0](http://creativecommons.org/publicdomain/zero/1.0/).  
Cheatsheet and this README are licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).
