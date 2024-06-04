# Build My Mac

[Xcode](#xcode)

[Homebrew](#homebrew)

[iTerm2 / oh-my-zsh](#iterm2--oh-my-zsh)

[Node via nvm](#node-via-nvm)

[Git Configuration](#git-configuration)

[Install More Apps with Homebrew](#install-more-apps-with-homebrew)

[Install Mac Apps with Homebrew "mas"](#install-mac-apps-with-homebrew-mas)

[More Installations and Configs](#more-installations-and-configs)

[M1 Troubleshooting](#m1-troubleshooting)

If needed accept and update the OS as prompted

During the initial setup you will:

- setup internet
- sign in with your apple ID

Recommended: change your password to something super simple JUST FOR SETUP and then change it to something more secure afterwards

Do yourself a favor and don't skip touch ID in the initial setup

To use your computer comfortably during setup:

- double check that your operating systems is up to date
- dock updates
  - remove all permanent dock items (right click to remove launchpad from dock)
  - update the dock placement and show/hide dock
  - turn off show recent applications in dock
- trackpad > turn on tap to click
- change the desktop background to something nice
- add at least your personal email to the Internet Accounts in System Preferences
- turn click on desktop to hide apps off
- Finder > View > Show Path Bar
- Finder > Settings > Advanced > deselect “Show all filename extensions”
- bump up time on lock screen/display sleep
- turn Off Guest User

## Xcode

Download Xcode, TestFlight, and Apple Developer from the AppStore

Open Xcode to see/accept any additional requirements or install any additional components

If they're not installed by Homebrew, you can install the XCode Command Line Tools from terminal by running:

```
xcode-select --install
```

If needed you can also accept the Xcode agreement from the terminal by running:

```
sudo xcodebuild -license accept
```

## Homebrew

Go to the homebrew site [here](https://brew.sh/)

From Terminal install Homebrew:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

This will also install the Xcode command line tools if that hasn't completed yet

Make sure to read the directions after the brew install completes to make add Homebrew to your PATH, then...

```
brew install git python watchman mas yarn
```

Note: [mas](https://github.com/mas-cli/mas) is a command line interface installed with homebrew to install mac app store applications

## To make your life easier -- 1Password, VSCode, FireFox, and 1Password Safari extension

```
brew install --cask 1password visual-studio-code firefox
```

```
mas install 1569813296
```

- open and setup 1Password, accept the accessibility settings as requested and add it to login items, then change quick access shortcut to `cmd + .`
- apple id > icloud > toggle off Password & Keychain
- open and setup Firefox and/or log into Firefox Sync
- open and setup VSCode with github sync
- open Safari and install 1Password extension

## iTerm2 / oh-my-zsh

For this you're going to want to run the below and then quit terminal and open iTerm

```
brew install --cask iterm2
```

Install oh-my-zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Add powerlevel10k theme with the zsh installation: https://github.com/romkatv/powerlevel10k#oh-my-zsh

Quit and reopen iTerm to run through the powerlevel10k wizard

Open and update .zshrc — remove uneeded boiler plate add aliases

My custom .zshrc additions:

```
plugins=(git z web-search)

# Preferred editor
  export EDITOR="code --wait"

# ALIASES
# For a full list of active aliases, run `alias`.
alias sourcez="source ~/.zshrc"
alias npm0="npm list -g --depth 0"
alias gs="git status"
alias gl="git log"
alias gcd="git checkout development"
alias gcm="git commit -m"
```

run

```
source ~/.zshrc
```

to apply those changes -- this will take you through the p10k prompts

iterm > preferences > profiles > window > adjust transparency to 30 and blur to 10
iterm > preferences > advanced > update scroll (look at other iTerm settings)

## Node via nvm

```
brew install nvm
```

- Follow the directions provided after the install and don't forget to run `source ~/.zshrc` or quit and reopen iTerm to apply those changes
- Verify that this has worked by running `nvm ls-remote 16` which will list all available versions of node v16
- Check out the [node docs](https://nodejs.org/en/about/releases/) to decide which version(s) of node you would like to install and then run `nvm install 00 --lts` which will install the latest stable version for that version node.
- To see your current config run `nvm list`
- For more options and config run `nvm -h`
- In any terminal if you want to see which version of node you are using run `node -v`.

## Git Configuration

Configure Git in the Terminal to sign your commits with your name and email address.

**WARNING:** Before running the following commands, replace `YOUR FULL NAME` and `YOUR EMAIL ADDRESS` with the name and email from [your GitHub account](https://github.com/settings/profile).

```
git config --global user.name 'YOUR FULL NAME'
git config --global user.email 'YOUR EMAIL ADDRESS'
```

run `git config --list` to check that you set these correctly

[Setting up GitHub SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

Repeat the SSH key process for any professional github/gitlab accounts

If you're setting up a second ssh key remember to change the name of the folder to `~/.ssh/id_[name]` to save as a new key.

## Install More Apps with Homebrew

[Karabiner-Elements](https://karabiner-elements.pqrs.org/docs/getting-started/installation/):

```
brew install --cask karabiner-elements && brew cleanup -s
```

- setup CAPSLOCK as global shortcut key: Complex Modifications > Add predefined rule > "Change caps_lock to command+control+option+shift"

Update Key Repeat from terminal:

```
defaults write -g ApplePressAndHoldEnabled -bool false
```

Other programs and utils:

```
brew install --cask alfred android-studio discord dropbox expressvpn flipper go google-chrome google-drive imageoptim keyboard-maestro obsidian rectangle rescuetime rocket screens-connect setapp skype slack sourcetree textexpander zoom && brew cleanup -s
```

## Install more Mac Apps with Homebrew "mas"

To find an app to install you can run `mas search [APPNAME]` returns a list of possible matches with codes.

Use mas to install Bear, Canva, Capcut, Deliveries, MetaPho, Mimeo, Moom, Spark, TandemDeviceUpdater, Word and Excel:

```
mas install 1091189122 897446215 1500855883 290986013 914457352 1282504627 419330170 1176895641 1100870281 462054704 462058435
```

Then run

```
brew cleanup -s
```

## More Installations and Configs

Open and log into all cask and mas installed apps -- special cases:

- Spark - add email accounts
- Setapp
  - install all favorited apps
  - BusyCal:
    - Add Calendar accounts
    - General > Week view shows > select "One Week" rather than "7 Days"
    - General > Start week on > "Monday"
    - add timezones
    - add tripsy calendar
- Rectangle (accept spectacle settings)
- TextExander (use license key)
- Obsidian + link to iCloud vault
- TestFlight - install Notability + turn on iCloud Syncing
- DropBox (includes config files for Alfred and Keyboard Maestro)
  - Alfred: use license key and restore from previous config
    - System Settings: Keyboard > Turn off Apple Spotlight, change cmd + space to Alfred
    - [Build and run alfred-maestro workflow](#Setting-up-Alfred-Maestro)
  - Keyboard Maestro: use license key and link to cloud config
- Google Drive
  - add accounts and add drives to Finder favorites
- Chrome + install [Google Meet Chrome PWA](https://support.google.com/meet/answer/10708569?hl=en)
- Xcode
  - sign into apple developer account
  - add new iOS versions: Preferences > Platforms > +
- Insomnia - [install v2023.5.8](https://github.com/Kong/insomnia/releases/tag/core%402023.5.8) then add profile.json from other installation
- Install Screens app from saved file

After Setup:

- check Allowed Notifications
- change password to something more secure (and put it in 1Password)
- turn back up time to sleep display
- add external keyboard and trackpad

## Android Studio

After using the Homebrew cask to install Android Studio:

- open the app and allow the initial build to complete, accepting the default options
- add a Pixel 5 API 31 emulator with the Device Manager
- add this to your .zshrc

  ```
  # Android
  export ANDROID_HOME=$HOME/Library/Android/sdk
  export PATH=$PATH:$ANDROID_HOME/emulator
  export PATH=$PATH:$ANDROID_HOME/platform-tools
  ```

## Java

Download and install [JDK17](https://www.oracle.com/java/technologies/downloads/#jdk17-mac)

Add this to your .zshrc

```
# Java
export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-17.jdk/Contents/Home
```

Remember to restart your terminal and then you can check that it is using the right version with `java --version`

## Ruby (with rbenv) and Cocoapods

Install [rbenv](https://github.com/rbenv/rbenv) with Homebrew

```
brew install rbenv ruby-build
```

Add this to your .zshrc

```
# rbenv
eval "$(rbenv init - zsh)"
```

Then install 2.7.5 (or whatever you need)

```
rbenv install 2.7.5
```

And set the version to be used globally

```
rbenv global 2.7.5
```

Remember to restart your terminal and then you can check that it is using the right version with `ruby -v`.

### bundler

When installing bundler you may get a notice about the latest version allowable for the version of ruby that you're using -- in the case of 2.7.5 the latest allowable bundler version is 2.4.22

```
gem install bundler -v 2.4.22
```

### Cocoapods

For an M Chip Mac:

```
sudo arch -arm64e gem install ffi
sudo arch -arm64e gem install cocoapods
```

To check this install navigate to the ios folder within the app and then run the below to confirm

```
pod install
```

## M1 Troubleshooting

### Ruby

If you're having trouble installing an older version of ruby you can try the steps outlined in this article on [how to install older versions of ruby on an M1 MacBook](https://stackoverflow.com/questions/69012676/install-older-ruby-versions-on-a-m1-macbook)

### Cocoapods

#### list any cocoapods/dependencies installed

```
gem list --local | grep cocoapods
```

#### uninstall them all

```
sudo gem uninstall cocoapods cocoapods-core cocoapods-deintegrate cocoapods-downloader cocoapods-plugins cocoapods-search cocoapods-trunk cocoapods-try
```

#### brew uninstall any version of ruby, rbenv, or ruby-build that is installed. You might have to use

```
brew uninstall ruby --force
```

#### Reinstall ffi and cocoapods with x86

```
sudo arch -x86_64 gem install ffi
sudo arch -x86_64 gem install cocoapods
```

Source: [Installing cocoapods for M1](https://stackoverflow.com/questions/66644365/cocoapods-on-m1-apple-silicon-fails-with-ffi-wrong-architecture/66771694#66771694)

# Other

### Setting up Alfred-Maestro

(For now) The M series chips require building the [Alfred-Maestro](https://github.com/iansinnott/alfred-maestro) workflow locally. This requires installing `go` with Homebrew (done above). After running the below, you can just open the workflow file from the directory as you would if you had downloaded it.

```
git clone https://github.com/iansinnott/alfred-maestro
cd alfred-maestro
make pack
```
