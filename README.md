# Duttsy package install
## Overview
the repo for installing [duttsy](https://github.com/LobotomizedHampster/duttsy.git)

## Install steps
### 1. Clone this repo
```bash
mkdir duttsy-install
cd duttsy-install
git clone (add name)
cd duttsy
```

### 2. Run the PKGBUILD
```bash
makepkg -si
```

### 3. (Optional) Delete the repo
```bash
cd ../..
rm -r duttsy-install
```

### Full code
```bash
mkdir duttsy-install
cd duttsy-install
git clone (add name)
cd duttsy
makepkg -si
#cd ../..
#rm -r duttsy-install
```
