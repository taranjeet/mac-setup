# mac-setup

## System Preferences

#### Trackpad

* Point & Click

  * Look up & data detectors with *Tap with three fingers*
  * Tap to click with *Tap with one finger*
  * Tracking Speed to *Fast*

#### Dock

* Check *Automatically hide and show the Dock*

#### Display

* Night Shift

 * Check *Turn On Until Tomorrow*

#### Users & Groups

* Disable Guest Login

#### Finder

* View
  * Switch to *as Columns*
  * Switch to *Arrange by* as *Name*
  
#### Menubar

* Change battery to display percentage

## Packages

### Xcode

```
xcode-select --install
```

### Brew

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Vim

```
brew install vim
```

### Generate ssh key

```
ssh key-gen
cat .ssh/id_rsa.pub
```

### Git

```
brew install git
```

### Iterm2

Download and install iterm2 from [here](https://www.iterm2.com/downloads.html)

#### Iterm2 Preferences

* Profiles

 * Terminal
  * Check Unlimited Scrollback

### Oh My Zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### Setup Dotfiles

Setup dotfiles from this [repo](https://github.com/taranjeet/dotfiles)

```
git clone https://github.com/taranjeet/dotfiles.git ~/.dotfiles
```

### Update Zsh Preferences

```
vim ~/.zshrc
for file in ~/.dotfiles/.{aliases,functions}; do
    [ -r "$file" ] && source "$file"
done
unset file

cp ~/.dotfiles/.gitconfig ~
```



