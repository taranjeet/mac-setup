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
  
 * Add Home folder in Sidebar
  * Open Finder, Press *Command + Shift + H*, then *Command + Up Arrow* and then drag and drop Home folder to side bar.
 
 * Remove *All My Files* from sidebar by right clicking and selecting *Remove from Sidebar*
  
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
cp ~/.dotfiles/.gitconfig ~

# edit zsh config
vim ~/.zshrc
for file in ~/.dotfiles/.{aliases,functions}; do
    [ -r "$file" ] && source "$file"
done
unset file

export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
```

### Sublime

Download Sublime 3 from [here](https://www.sublimetext.com/3). Setup `subl` alias to open Sublime from command line

```
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

* Install Package Control from [here](https://packagecontrol.io/installation)
* Install [Dracula Color Theme](https://draculatheme.com/sublime/) using Package Control
* Keep the icon for Sublime in Dock by right clicking on the running application, then selecting *Options* and then *Keep in Dock*. 

### Python

```
brew install python@2
# check if python and pip both are pointing to version 2

pip install virtualenv
```

### Node.js

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
source ~/.zshrc
nvm install v8.9
```

### Youtube dl

```
brew install youtube-dl
```

### Flycut

Install flycut from [here](https://github.com/TermiT/Flycut/releases). Update Flycut Preferences as

* Check *Launch FLycut on login*

### Htop

```
brew install htop
```

