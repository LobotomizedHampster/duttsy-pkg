# START GUIDE

# ======= IMPORTANT ========
So as you can tell from the amount of stars this has, this is not a very popular repo (and for good reason, my coding abilities are summed up by my username). And since its so unpopular, I haven't bothered writing the docs. So if you happen to come across this text, feel free to leave an issue, and, assuming I'm still using this account, I'll finish them. (though i will say, most if it is either already covered or self explanatory.).

## Before Continuing...
...understand what this program is and what it does (and, more importantly, what is does not do).

### What this Program Does
- creates symlinks to files in the `~/.dotfiles/` directory 
- structures the files as if in your home directory
- allows for unlinking files through the --deltete flag
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
This the `~/.dotfile` directory is where all of the files that you want to track will be.
To add:
```bash
mkdir ~/.dotfiles
```

#### Step 2: Track your first file
To start tracking a file, copy it to the dotifles directory. In this example, we will move the .xinitrc file.
```bash
cp ~/.xinitrc ~/.dotfiles/.xinitrc
```

Now the home directory structure looks like this:
```
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
├── .dotfiles/   
│   └── .xinitrc   <--- copied file
└── .xinitrc   <--- notice that .xinitrc is still in the home dir
```
Note: `.xinitrc` _can_ be removed from the home directory, but its not necessary. The program will take care of this automatically

Now, run the program:
```bash
duttsy
```


If done correctly, the structure should now look like this:
```
/home/user/
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
├── .dotfiles/
│   └── .xinitrc
└── .xinitrc -> .dotfiles/.xinitrc   <--- the "<-" means its symlinked to that file
```

As you can see, the `.xinitrc` file in home is now symlinked to the file in `.dotfiles/` everything should behave as it normally does, other than the fact that you can now edit the file in `.dotfiles/`
