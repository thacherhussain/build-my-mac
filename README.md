# Build My Mac

Before getting started make sure that your operating systems is up to date
### XCode

Install XCode from the AppStore

Install XCode Command Line Tools from terminal: `xcode-select --install`

Accept the Xcode agreement from the terminal: `sudo xcodebuild -license accept`

Open XCode to see/accept any additional requirements or install any additional components

### Install nvm and node

Before installing nvm make sure you have created a `.zshrc` or `.bashrc` file. 

This article goes through [How to install Node.js and npm on macOS](https://www.newline.co/@Adele/how-to-install-nodejs-and-npm-on-macos--22782681)


Install nvm to manage you node versions
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

Using nvm install the version(s) of node you want -- when in doubt go with the latest LTS version with the following commands:

```
nvm install --lts
```

### Install Homebrew, Brew Apps and Casks

Install Homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Install Java 8
```
brew tap AdoptOpenJDK/openjdk
brew install --cask adoptopenjdk8
```

```
brew install git zsh z watchman gradle
```

#### Install Brew Casks
These applications are based on my personal preferences

```brew install
1password
alfred
android-studio
atom
firefox
gitkraken
google-backup-and-sync
google-chrome
hazel
iterm2
karabiner-elements
keyboard-maestro
omnifocus
pock
rescuetime
robo-3t
skype
slack
spectacle
spotify
textexpander
visual-studio-code
yarn
zoomus
```

Install MS Office Separately because it requires confirmation with a pop-up
`brew install microsoft-office`

Install Notes: 
- [karabiner-elements](https://karabiner-elements.pqrs.org/docs/getting-started/installation/)

### Install Mac Apps with Homebrew "mas"
[mas](https://github.com/mas-cli/mas) is a command line interface installed with homebrew to install mac app store applications 

```brew install mas```

Notability: `mas install 736189492`
Bear: `mas install 1091189122`
Deliveries: `mas install 290986013`


### Install Expo CLI (for use with React Native development)
`npm install -g expo-cli`

### iTerm Config

##### Oh My Zsh
[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

#### Setting up Zsh
Follow [fishToZsh Repo](https://github.com/thacherT1D/fishToZsh) to change shell, add zsh plugins, update theme, and add powerline fonts

#### .zshrc file config with custom scripts
Add the following and delete anything extraneous

```
ZSH_THEME="af-magic"
plugins=(git node npm osx z)
```

### Git Configuration
#### Configure Git in the Terminal
Let's configure Git to sign your commits with your name and email address.

**WARNING:** Before running the following commands, replace `YOUR FULL NAME` and `YOUR EMAIL ADDRESS` with the name and email from [your GitHub account](https://github.com/settings/profile).

```
git config --global user.name 'YOUR FULL NAME'
git config --global user.email 'YOUR EMAIL ADDRESS'
```

#### Setup Git SSH Keys
[Git Article on setting up SSH Keys](https://help.github.com/articles/connecting-to-github-with-ssh/)


**To use your computer comfortably now:**
- Keyboard > Turn off Apple Spotlight, change cmd + space to Alfred
- Turn Off Guest User
- Update Desktop Image
- Dark Mode
- Trackpad > turn on tap to click


### Other Installs
- Setapp

#### Post Script Installations and Configs
- Dock Icons, Order, and Zoom
- Finder > View > Show Path Bar
- Activate Accounts to System Preferences
- Notifications
- Slack Teams
- 1Password - Sign in and shortcut set to option + space
- Hazel - link with cloud config file
- Keyboard Maestro - link with cloud config file
- Setapp - sign in and download apps: Bartender, ChatMate, CleanMyMac, Endurance, iStat Menus, Sip, ToothFairy, WorldClockPro

##### And then...

- Update Key Repeat from terminal ```defaults write -g ApplePressAndHoldEnabled -bool false```