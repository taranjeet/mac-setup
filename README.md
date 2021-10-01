# mac-setup

## System Preferences

#### Trackpad

* Point & Click

  * Look up & data detectors with *Tap with three fingers*
  * Tap to click with *Tap with one finger*
  * Tracking Speed to *Fast*

#### Dock

* Check *Automatically hide and show the Dock*
* Change Dock Size settings to Small

#### Display

* Turn off True Tone settings.

* Night Shift

 * Check *Custom* and set the timings. Change Color Temperature to *More Warm*

#### Users & Groups

* Disable Guest Login

#### Finder

* View
  * Switch to *as Columns*
  * Switch to *Sort by* as *Name*
  
 * Add Home folder in Sidebar
  * Open Finder, Press *Command + Shift + H*, then *Command + Up Arrow* and then drag and drop Home folder to side bar.
 
 * Remove *All My Files* and *Recents* from sidebar by right clicking and selecting *Remove from Sidebar*.
 * Under *Finder Preferences > General* select *New Finder windows show:* option to *Home directory name*
 * Under *Finder Preferences > Advanced*, select *When performing a search:* option to *Search the Current Folder*
  
#### Menubar

* Change battery to display percentage
* Hide *Bluetooth* and *Display* icon in the menubar.

#### Mission Control

* Uncheck *Automatically rearrange Spaces based on most recent use*

#### Keyboard

* Keyboard
    * Set *Key Repeat* to *Fast*
    * Set *Delay Until Repeat* to *Short* 

* Text
    * Uncheck *Add full stop with double-space* under *Text* section.

#### Spotlight

* Uncheck *fonts*, *images*

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

    * Text
        * Set *Cursor* style to *underline*
        * Check *Blinking cursor*
        * Update font size to 14pt

    * Keys
       * Follow this [link](https://coderwall.com/p/h6yfda/use-and-to-jump-forwards-backwards-words-in-iterm-2-on-os-x) to jump words backward/forward.
       * Follow the above link only and now add sequence to jump to start/end of line.


| Shortcut | Action               | Esc+ |
|:--------:|:--------------------:|:----:|
| ⌘←	      | Send Escape Sequence | OH   |
| ⌘→		     | Send Escape Sequence | OF   |


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


### Visual Studio Code

```
brew install --cask visual-studio-code
```


### Bash Completion

Install bash completion by running

```
brew install bash-completion

# add following to .bash_profile or .zshrc
[[ -r "/opt/homebrew/etc/profile.d/bash_completion.sh" ]] && . "/opt/homebrew/etc/profile.d/bash_completion.sh"
```


### Python

```
# python3 is by default installed

pip3 install virtualenv
```

### Youtube dl

```
brew install youtube-dl
```

### Flycut

Install flycut by running

```sh
brew install --cask flycut
```

* Update Flycut Preferences as
    * Check *Launch Flycut on login*
    * Check *Sticky Bezel*

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

### Install Asana, Notion, Spotify, Vlc Zoom

```
brew install --cask asana notion spotify vlc zoom
```

### Install Heroku

```
brew tap heroku/brew && brew install heroku
```



### Custom folders

```
mkdir ~/myapps
```

### Mysql

* Follow [this post](https://gist.github.com/wpconsulate/40469bfdafad9fdd0afc3e260a5586a7) to install Mysql 5.7

### Chromedriver

* Install by running

```
brew install --cask chromedriver
```

* Follow [this post](https://stackoverflow.com/questions/60362018/macos-catalinav-10-15-3-error-chromedriver-cannot-be-opened-because-the-de) to give appropriate permissions.

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

<details>
  <summary>Old Config and Packages</summary>
  
### Evernote

Download evernote from this [link](https://evernote.com/download)
 
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

### Node.js

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
source ~/.zshrc
nvm install v8.9
``` 

### Custom Python packages

```
pip install grip
```

### Custom Npm packages

```
npm install -g create-react-app
```
</details>

