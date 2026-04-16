# START GUIDE
## Before Continuing...
...understand what this program is and what it does (and, more importantly, what is does not do).

### What this Program Does
- creates symlinks to files in the `~/.dotfiles/` directory 
- structures the files as if in your home directory
- allows for unlinking files through the --delete flag
- ignores files/folders specified in the `~/.dotfiles/.duttsy-ignore` file.
- manages symlink conflicts through the `~/.dotfiles/.overwritten` folder

### What this Program Does Not Do
- automatically version your symlinked files (use git or another similar tool)
- allow changing the name of the dotfiles or overwritten folders

### One More Important thing
This program was written over the cause of about four days, there are bugs. So when using the program, understand that there are glitches that can occur, and there could potentially be data loss.

## Installation
It is recommended you install duttsy before continuing with this guide. If you have not already installed duttsy yet, follow the instructions in the [README.md](../README.md)

## Tracking Dotfiles
I think the best way to show how to use the program is though an example.

### Example Set Up
Lets say your home directory looks like this:
```
home/user/
├── .config/
│   ├── kitty/
│   │   ├── colorscheme.conf
│   │   └── kitty.conf
│   ├── nvim/
│   │   ├── init.lua
│   │   └── lazy.lock.json
│   └── vlc/
│       ├── vlc-qt-inerface.conf
│       └── vlcrc
└── .xinitrc
```

And lets say you want to track only the files/folders listed below:
- `~/.xinitrc`
- `~/.config/nvim/init.lua`
- `~/.config/kitty/`

### How To

#### Step 1: Create the dotfile directory

