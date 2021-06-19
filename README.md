# ErgoVim

> If you use UK style or DVORAK keyboard, or something like HHKB,  
> ErgoVim may not work as intented.  
> 
> This README assume you use **STANDARD** US style keyboard.

---

## Introduction

ErgoVim is a ergonomic keymapping for Vim.

Design for comfort, ease of reach, intuition and area relationships,  
rather than naming gimmicks.

Also, ErgoVim is minimal (but not basic) and easy to reason about,  
so you can customize/extend it to your needs with low friction.

> Your hands are much faster than your brain.

---

## How to Install

- Vimer that already have a setup:
    
    0. ErgoVim breaks **EVERYTHING** from classic Vim.  
    **DON'T** directly copy this vimrc to your vim config or plugin folder.  
    **BACKUP** your setup first.  

    1. Download from [release](https://github.com/Letheward/ErgoVim/releases) or clone this repository.
    
    2. Read the source code, cheatsheet and "How to Use" carefully,  
    make sure you understand the philosophy behind those design choices.

    3. Figure out how to integrate the keymap to your own setup.
 
- Using Neovim with no setup:

    1. Open Neovim, type `:echo stdpath('config')` and Enter. 
    It will output something like this: `C:\Users\You\AppData\Local\nvim`. (this is on windows)
    
    2. Go to that folder, if there is none, create a `nvim` folder in the upper folder.
    
    3. Close Neovim by typing `:qa!` and Enter.

    4. Download from [release](https://github.com/Letheward/ErgoVim/releases) or clone this repository.

    5. Rename the `vimrc` in extracted folder to `init.vim`.
    
    6. Put `init.vim` to the folder in step 1. 

    7. Open Neovim again, you may notice something has changed.  
    Hit \` key, type `qa!` and Enter to exit.

- Using vanilla Vim with no setup:

    1. Open Vim and type `:version`, hit `Enter`. It will output something like this:  
    (you may need to hit `Enter` to scroll down to see all of it, keep it open so you can refer to)

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

    2. Go to directories:
        - `system vimrc file`
        - `user vimrc file`
        - `2nd user vimrc file`

        If you are using MinGW, they might endup being in your MinGW distro's `/etc/`, etc.  

    3. Check if there are already vimrc files. (they may be hidden in file explorer)  
        If so, **COPY** them to a secure location.
    
        Make sure you put them in separate folders to distinguish them.

    4. Download from [release](https://github.com/Letheward/ErgoVim/releases) and extract, or clone this repository.

    5. Choose one from these 3 directories to install ErgoVim.  
    Rename the `vimrc` file from ErgoVim to the name in the directory you choose.  

        - If you are using MinGW on Windows, `system vimrc file` is recommended.
        - If you don't know how to delete files in protected `/etc/`,  
        you can rename it to the one in `user vimrc file`.
        - If you want to install to `2nd user vimrc file`,  
        you may need to create a `.vim` folder if there is none.

    6. Close Vim. If you don't know how:

        - hit `Enter` to close that output window if it's still open.
        - Now type `:qa!`, hit `Enter`.

    7. Now delete the **ALL** the original `vimrc` files in these directories.  
        **Be careful** not to accidently delete other files.  

        Then put your renamed `vimrc` to the directory you choose.  

    8. Open Vim again, you may notice something has changed.

    9. Hit \` key (it's on the upside of `Tab`), and type `qa!`, hit `Enter`. It should close.  
    If not, close Vim using the old method,  
    back to step 1, check for errors, and repeat. 

    999999999. After you are familiar with Vim, look into the older `vimrc` files.  
    Get features you want back to you config.

---

## How to Use

![cheatsheet](img/Cheatsheet.png)
(the cheatsheet, right-click/long-press to download if text is too small on your device)  
(also there is a copy in the zip download from [release](https://github.com/Letheward/ErgoVim/releases))

### First Steps

First, you need to understand that Vim is a modal Editor.  
That means, there are different modes in Vim.  

There are at least 3 modes you need to use:

- Normal Mode  
    For navigation, cut/copy/paste and much more.  
    This is the "home" mode in Vim.

- Command Line Mode  
    For entering commands like quit Vim, open and save your file, etc.

- Insert Mode  
    Enter your text like in a normal editor.

When you open Vim, Normal Mode is the default mode you are in.  
Hit `Esc` to exit most modes.

Let's do a step-thru exercise:

- Part I
1. Open Vim.
1. Naturally rest your left hand on `wasd`, right hand on `ijkl`.
1. Hit `ll` to enter Insert Mode.
1. Enter some gibberish, need to have spaces and blanklines. 
1. Enter more gibberish like above.
1. Enter even more gibberish that you need to scroll the screen.
1. Hit `Esc` to back to Normal Mode.
1. Use `wasd` to navigate, like using a game controller's D-Pad.
1. Use `qerf` to navigate, observe the differences.
1. Use `WASD` (capital means with `Shift`) to navigate.
1. Navigate some more.

- Part II
1. Navigate to middle of a long word, hit `k`, hit more if you want.
1. Now try hit `K` instead.
1. Now hit `u` repeatly until the full word is back.
1. Hit `U` repeatly until nothing happens. 
1. Press and hold `u` until the file is back to empty.
1. Press and hold `U` until nothing happens. 
1. Hit `m` Key to enter Visual Mode.
1. Try navigate using everything you know, observe what happens.
1. Hit `Esc` to back to Normal Mode.
1. Enter Visual Mode again, but now hit `m` to back.

- Part III
1. Hit \` Key to enter Command Line Mode.
1. Input some *really really long* gibberish and hit `Enter`.
1. Enter Command Line Mode again, this time type `help cmdline` and hit `Enter`.
1. If you want to read that, navigate using the same method you learned.
1. Hit `xk` to close that help window.
1. Hit `xk` again.
1. Enter Command Mode, try `quit`.
1. Enter Command Mode again, try `q`.
1. Enter Command Mode again, try `q!`.

### Basic Editing

### Key Sequences

### Window Management

### Advance Editing

### The Philosophy

The core ideas of ErgoVim are:

1. Hands should rest naturally on the keyboard.
2. Everything should be done with minimal motion.
3. Design should make users think less about the editor.

To accomplish these, ErgoVim has some design choices:

- Area Relationship:

    - Left Hand is mainly for movements.  
    - Right Hand is mainly for actions.
    - Bottom row is basically all about window/view/position.
    - In text object, left hand is for all the syntax structures,  
    and structures in each row are similiar.

- Semantic Key Sequences:

    - Following Direction Keys:

        - `ld` is insert to the *right* of this line.
        - `jf` is cut *down the block*.
        - `ie` is copy until the *word right*.

    - Following Action Keys:

        - (same as leader, like `jj`, `ii`, `xx`) do the basic stuff
        - `l` Enter, Confirm, do things
        - `k` cancel, delete, exit, close
        - `j` change, cut, join
        - `i` copy, identity
        - `n` new

Examples:

- `xna`: open a *window* to edit *new file*, to the *left*.  
- `Zl`: *entering* the fold.  
- `nk`: *cancel* search highlight.   
- `ni`: *search* using the word under *current* cursor location. 

### Tips

- Don't try to memorize/utilize everything at once. Get the basic stuff done first, then gradually build up your muscle memory.

- Use large motions for fast move.

- Avoid using your pinky as possible:

    ErgoVim tries very hard to minimize pinky usage, however there are inevitably some features need `Shift` and `Ctrl`.  
    In those cases, since those features are less frequent by design, you should use your stronger fingers/both hands,  
    without worrying about speed loss for moving your hands out of homerow.

    Also, if you need to hit `Tab` repeatly (like auto-complete in `cd`), you should use a stronger finger (or even multiple fingers) to do that.


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

---

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


---

## Q&A

- > Vim is already ergonomic.

    We may have very different understandings of the word "ergonomic".

- > My favorite Vim features are missing.

    You can try to translate them to the style of new design, and check if there is room in key sequence namespaces for them.

- > I am left handed/used to right hand on Arrows/have only one hand.

    ErgoVim will be nonetheless a new mapping for you, so you can choose to learn it the original way.  

    Or, understand ErgoVim philosophy and remap everything yourself, this should be easy to reason about, but tedious to do (just like developing ErgoVim against classic Vim).  
    In the end, if that makes you use Vim better, it's worth it, because software should adjust to people, not the other way around.

- > Why don't you remap `Esc` with something like `jk` or `jj`?

    Because sometimes you do need to write `jk` or `jj`, and when you type `j` you will think not type `k`, which slows you down and will mess up your flow.

    Change `jk` to anything else uncommon that you can type as text won't work either.  
    The Proof: How do you write your keymap manual using Vim with your new `Esc` remap?

- > How about `Alt` and `CapsLock` ?

    These Keys don't work consistently across multiple OS/Terminals.  
    Typical `CapsLock` / `Esc` / `Ctrl` swap is done by registry hack/OS config/AHK, etc.

    If you know how to fix the problem by vimscript only,  and get it work on every major platform, please do PR or write a issue.

- > Why put so much effort on a keymapping?

    Because keymapping is really important. If you don't believe that, try play a FPS with Emacs navigation controls.

    Secondly, Vim keymapping is not just swap keys. Vim is not a text editor, but a half-ass (better than nothing) key sequence/macro interpreter, plus a extendable text editor loaded with insane amount of commands.  
    
    If you understand that, you can do super crazy stuff with mapping that will massively speed you up (assume you can remember it). With that said, ErgoVim is not a crazy stuff config, but a friendly starting ground.

- > Why don't you make your own editor/fork Vim?

    It could happen, but not right now.

- > Is ErgoVim inspired by modern video games?

    Yes. (also Japanese style PlayStation Controller Mapping)  
    (I still don't understand how tf `X` is confirm, `O` is cancel, or on the left is continue, on the right is cancel... please.)

---

## Known Issues

This `vimrc` file is already tested on:
- Vim 8.2 (huge version), MinTTY/MinGW, Windows 10. (developed on)
- Vim 8.1 (huge version), Konsole/X11/KDE Plasma 5.21.5, KDE Neon 5.21. (no problem found yet)
- Vim 8.2 (small version), GNOME Terminal/Wayland/GNOME 3.38.1, Fedora 33. (partially working)
- Neovim v0.4.4, nvim-qt, Windows 10. (minor issues)

Issues:
- Some Commands will behave like the old way if it's hold other than tapped.
- Search back will perform once more if hold (due to how it's designed), wait for it or hit `Shift-N` to cancel.
- Default small version Vim miss many features, like text object, auto-complete, etc.   
    Using key sequences for those features may cause unwanted behavior.
- `Shift-Enter` on GNOME Terminal/Fedora 33 is not working.
- Terminal window switching is not ideal.
- On Neovim, Visual mode cursor `a` and `d` may need extra input to function.
- Terminal on Neovim is not working as expected.

## License

The `vimrc` file is dedicated to public domain, or under [CC0](http://creativecommons.org/publicdomain/zero/1.0/).  
Cheatsheet and this README are licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).
