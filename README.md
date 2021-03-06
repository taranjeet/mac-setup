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

#### Mission Control

* Uncheck *Automatically rearrange Spaces based on most recent use*

#### Keyboard

* Text
  * Uncheck *Add period with double-space*

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

 * General
  * Check *Reuse previous session directory* under *Working Directory*

 * Terminal
  * Check Unlimited Scrollback
 
 * Follow this [link](https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x) to jump words backward/forward.

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

# maintain history per tab level
unsetopt inc_append_history
unsetopt share_history
```

### Sublime

Download Sublime 3 from [here](https://www.sublimetext.com/3). Setup `subl` alias to open Sublime from command line

```
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

* Install Package Control from [here](https://packagecontrol.io/installation)
* Install [Dracula Color Theme](https://draculatheme.com/sublime/) using Package Control
* Keep the icon for Sublime in Dock by right clicking on the running application, then selecting *Options* and then *Keep in Dock*.
* Change Sublime Color Scheme by *Sublime Text > Preferences > Settings* and then selecting *Dracula* as the option.
* Install sublime packages from [dotfiles](https://github.com/taranjeet/dotfiles) repo.
* Configure Babel to open jsx file as babel intrepreted by following this [link](https://github.com/babel/babel-sublime#setting-as-the-default-syntax)

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

### Wget

```
brew install wget --with-libressl
```

### Tree

```
brew install tree
```

### Custom Python packages

```
pip install grip
```

### Custom Npm packages

```
npm install -g create-react-app
```

### Custom folders

```
mkdir binaries myapps
```

### Mysql

```
# install mysql 5.6
brew install mysql
brew postinstall mysql
mysql_secure_installation
login to shell and run the following query
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

### Java

Download jdk 8 from this [link](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) after accepting the Agreement Terms. Open dmg and follow through the setup process. Check if java is installed properly by running

```
java -version
```

### Elasticsearch

Download tar file of required version of elasticsearch from [here](https://www.elastic.co/downloads/elasticsearch). When writing this doc, the latest version is *6.3*. Move the tar to `binaries` folder and extract it.

```
mv ~/Downloads/elasticsearch-6.3.1.tar.gz ~/binaries
tar -xvzf elasticsearch-6.3.1.tar.gz

# to run
./bin/elasticsearch
```

#### Update Elasticsearch preferences

In `config/elasticsearch.yml`, update `cluster.name` to a custom value.

In `config/jvm.options`, remove `-Xms1g` and `-Xmx1g`, and add the following

```
-Xms500m
-Xmx500m
```

### Kibana

Download the tar file of required version(latest 6.3) from [here](https://www.elastic.co/downloads/kibana). Move the tar to `binaries` folder and extract it.

```
mv Downloads/kibana-6.3.1-darwin-x86_64.tar.gz binaries/
tar -xvzf kibana-6.3.1-darwin-x86_64.tar.gz
```

### Vlc

Download vlc from this [link](https://www.videolan.org/vlc/download-macosx.html)

### Evernote

Download evernote from this [link](https://evernote.com/download)

### MTMR

Download MTMR from [here](https://github.com/Toxblh/MTMR) and use the following preferences

```
[
    {
        "type": "escape",
        "width": 64,
        "align": "left"
    },
    { "type": "brightnessDown", "width": 56, "bordered": true, "align": "left" },
    { "type": "brightnessUp", "width": 56, "bordered": true, "align": "left" },
    {
        "type": "nightShift",
        "width": 36,
        "align": "left"
    },
    {
        "type": "appleScriptTitledButton",
        "source": {
            "inline": "if application \"Spotify\" is running then\rtell application \"Spotify\"\rif player state is playing then\rreturn (get artist of current track) & \" – \" & (get name of current track)\relse\rreturn \"\"\rend if\rend tell\rend if\rreturn \"\"\r"
        },
        "action": "appleScript",
        "actionAppleScript": {
            "inline": "if application \"Spotify\" is running then\rtell application \"Spotify\"\rif player state is playing then\rnext track\rend if\rend tell\rend if\r"
        },
        "refreshInterval": 1,
        "image": {
            "base64": "iVBORw0KGgoAAAANSUhEUgAAAEAAAABABAMAAABYR2ztAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAAYUExURUdwTB3WXx3UXh3VXx7XYBkXFRpVLRyURmIaeAQAAAAEdFJOUwDDO3fSqUUkAAABbklEQVRIx61VbW6DMAztoAeYNA7ApB6gkzhAWS24wIAL0HABaK6/pHFNEhy8TXu/kPzkPD/8cTj8K7KPAqB+K5NhQPCUrABCXe7HOUYYZxgVRLiG8RfY4DUgFFtC7cffAfZTFBwBdhWEKfgEq4ocEjgj4ZQifO6/QG9kkETp1dDeVWfRKx3XYSW0LoqY5kCElXDrQkyeCCuh6WL0M4nIWQIyzqixdfKU1koFDKvyCA8NJMzU4xiD+b4kfHRpsIyKc6hBwjVptFHVY51EMAINNDFGJITKDNQcdpX74Hz0CQ3rY5qwMp4EIxrlafzrsYZ2Veb0DkRgfNCUok4Y1fqEijfyi2b8RE9beWqa48Y/uvCNMcH9btfUi+/CGLR1vhL6Zz9N/vBlaCU+7lwY/cmJ67Ryen/2tj23PLqJBodZH8vgj544vOL4pxfI5acrSFxi8hrkU9TSKr78ZpnL50A8KPJJEo+afBblwyqf5j/iGys5j6ScrST2AAAAAElFTkSuQmCC"
        }
    },
    {
        "type": "previous",
        "width": 56,
        "align": "right"
    },
    {
        "type": "next",
        "width": 56,
        "align": "right"
    },
    
    {
        "type": "play",
        "align": "right",
        "width": 56
    },
    {
        "type": "mute",
        "width": 56,
        "align": "right",
        "bordered": true
    },
    {
        "type": "volume",
        "width": 130,
        "align": "right"
    },
    {
        "type": "timeButton",
        "formatTemplate": "HH:mm",
        "align": "right",
        "bordered": false,
        "longAction": "shellScript",
        "longExecutablePath": "/usr/bin/pmset",
        "longShellArguments": ["sleepnow"]
    },
    {
        "type": "exitTouchbar",
        "width": 56,
        "align": "right"
    },
]
```
