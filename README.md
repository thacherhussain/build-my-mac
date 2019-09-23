# Build My Mac

### Update Operating System

Go to App Store and run any operating system updates (this may take a bunch of iterations)
In Mojave OS updates are in System Preferences > Software Update

### XCode

Install XCode from the AppStore

Install XCode Command Line Tools from terminal: `xcode-select --install`

Accept the Xcode agreement from the terminal: `sudo xcodebuild -license accept`

Open XCode to see/accept any additional requirements or install any additional components


### Install Homebrew, Brew Apps and Casks
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

```
brew install git vim bash zsh z postgresql mysql node watchman
```

```
brew cask install java
brew install gradle
```

```
brew install heroku/brew/heroku
brew 'homebrew/cask-drivers/luna-display'
```

```
brew cask install iterm2 spectacle alfred google-chrome flycut 1password atom visual-studio-code yarn
```

Install nvm to manage you node versions
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

Install React Native
```
npm install -g expo-cli
```

### Setup 1Password
Sign in and shortcut set to option + space


### Configure Git
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


### iTerm Config

##### Oh My Zsh
[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

#### Setting up Zsh
Follow [fishToZsh Repo](https://github.com/thacherT1D/fishToZsh) to change shell, add zsh plugins, update theme, and add powerline fonts

#### .zshrc file config with custom scripts
(Pending)

### Other Brew Casks
```brew cask install astropad firefox google-backup-and-sync keyboard-maestro hazel jetbrains-toolbox minecraft microsoft-office mysqlworkbench rescuetime slack spotify skype whatsapp zoomus textexpander vscode```

### Mac Apps with Brew
```brew install mas```

Airmail 3: ```mas install 918858936```

Day One: ```mas install 1055511498```

Notability: ```mas install 736189492```

Bear: ```mas install 1091189122```

### Other Installs
- Omnifocus (Mac App Store)
- [Setapp](https://setapp.com)
    Bartender, ChatMate, CleanMyMac, Endurance, iStat Menus, Sip, ToothFairy, TripMode, WorldClockPro

- [iGlasses](https://www.ecamm.com/mac/iglasses/)
- [Android Studio](https://developer.android.com/studio/install#mac)

#### Post Script Installations and Configs
- Dock Icons, Order, and Zoom
- Finder > View > Show Path Bar
- Activate Accounts to System Preferences
- Slack Teams
- Hazel - link with cloud config file
- Keyboard Maestro - link with cloud config file

<hr>

#### To Add
- git kraken
- karabiner elements
- Pock
- Rescue Time
- Deliveries

<hr>

### Java (as needed/wanted)
#### Java 8
Download and install [Java 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

##### And then...
- Install [MySQL Community Server](https://dev.mysql.com/downloads/mysql/)

- Key Repeat ```defaults write -g ApplePressAndHoldEnabled -bool false```
