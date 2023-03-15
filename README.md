# Build My Mac

[Xcode](#xcode)

[Homebrew](#homebrew)

[iTerm2 / oh-my-zsh](#iterm2--oh-my-zsh)

[Node via nvm](#node-via-nvm)

[Git Configuration](#git-configuration)

[Back to Homebrew](#back-to-homebrew)

[Setting stuff to set stuff up](#setting-stuff-up-to-set-stuff-up)

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

- remove all permanent dock items (right click to remove launchpad from dock)
- trackpad > turn on tap to click
- update the dock placement and show/hide dock
- turn off show recent applications in dock
- change the desktop background to something nice
- Add at least your personal email to the Internet Accounts in System Preferences
- double check that your operating systems is up to date
- turn off hot corners
- bump up time on lock screen/display sleep

After Setup:

- change password to something more secure (and put it in 1Password)
- turn back up time to sleep display

## Xcode

Download Xcode from the AppStore

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

make sure to read the directions after the brew install completes to make add Homebrew to your PATH

then use homebrew... `brew install git python watchman`

## iTerm2 / oh-my-zsh

For this you're going to want to `brew install --cask iterm2 visual-studio-code`
then quit terminal and open iTerm

and a helper if you'd like `brew install --cask spectacle` then open spectacle and allow it to install and then open it again after install, update the accessibility settings as requested and add it to login items

Install oh-my-zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Add powerlevel10k theme with the zsh installation: https://github.com/romkatv/powerlevel10k#oh-my-zsh

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

run `source ~/.zshrc` to apply those changes -- this will take you through the p10k prompts

iterm > preferences > profiles > window > adjust transparency to 30 and blur to 10

## Node via nvm

```
npm install -g npm
```

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

`brew install --cask 1password`

- open and setup 1Password, accept the accessibility settings as requested and add it to login items, then change quick access shortcut to `cmd + .`

Configure Git in the Terminal to sign your commits with your name and email address.

**WARNING:** Before running the following commands, replace `YOUR FULL NAME` and `YOUR EMAIL ADDRESS` with the name and email from [your GitHub account](https://github.com/settings/profile).

```
git config --global user.name 'YOUR FULL NAME'
git config --global user.email 'YOUR EMAIL ADDRESS'
```

run `git config --list` to check that you set these correctly

[Setting up GitHub SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

## Back to Homebrew

```
brew install yarn
```

```
brew install --cask obsidian firefox
```

## Setting stuff up to set stuff up

- apple id > icloud > toggle off Password & Keychain
- add/login into Accounts — at least personal gmail
- open and setup Firefox and/or log into Firefox Sync
- open VScode, login to sync settings
- open Obsidian and link to iCloud vault

## Install More Apps with Homebrew

For Work:

```
brew install --cask slack google-drive google-chrome zoom
```

[Karabiner-Elements](https://karabiner-elements.pqrs.org/docs/getting-started/installation/):

```
brew install --cask karabiner-elements
```

Misc small things:

```
brew install --cask rocket alfred rescuetime textexpander keyboard-maestro setapp spotify expressvpn sourcetree dropbox
```

If you want to do all this in one go...

```
brew install --cask slack google-drive google-chrome zoom karabiner-elements rocket alfred rescuetime textexpander keyboard-maestro setapp spotify expressvpn sourcetree dropbox
```

Then run `brew cleanup -s`

## Install Mac Apps with Homebrew "mas"

[mas](https://github.com/mas-cli/mas) is a command line interface installed with homebrew to install mac app store applications

```
brew install mas
```

Find an app to install:

`mas search Spark` returns a list of possible matches with codes

`mas install 1176895641`

Spark: `mas install 1176895641`

Bear: `mas install 1091189122`

Deliveries: `mas install 290986013`

Moom: `mas install 419330170`

TestFlight: `mas install 899247664`

All together now:

```
mas install 1176895641 1091189122 290986013 419330170 899247664
```

If needed, install MS Office Separately because it requires confirmation with a pop-up:

Word: `mas install 462054704`

Excel: `mas install 462058435`

All together:

```
mas install 462054704 462058435
```

Seems like you actually have to download these from the sites...

[postgres app](https://postgresapp.com/)

[devonthink 3](https://www.devontechnologies.com)

Then run

```
brew cleanup -s
```

## More Installations and Configs

- Install Notability from Test Flight
- Finder > View > Show Path Bar
- Activate other Internet Accounts
- Check Allowed Notifications
- Turn Off Guest User
- Slack Teams
- Open TestFlight and install Notability
- Keyboard Maestro - link with cloud config file
- Setapp - sign in and download favorited apps and config
- BusyCal - View > Days in Week > select "One Week" rather than "7 Days"
- Alfred
  - restore from previous config
  - Keyboard > Turn off Apple Spotlight, change cmd + space to Alfred
-
- Sign into text expander
- Xcode
  - sign into apple developer account
  - add new iOS versions: Preferences > Platforms > +

Update Key Repeat from terminal:

```
defaults write -g ApplePressAndHoldEnabled -bool false
```

## M1 Troubleshooting

### Ruby

If you're having trouble installing an older version of ruby you can try the steps outlined in this article on [how to install older versions of ruby on an M1 MacBook](https://stackoverflow.com/questions/69012676/install-older-ruby-versions-on-a-m1-macbook)

### Cocoapods

    # list any cocoapods/dependencies installed

    gem list --local | grep cocoapods


    # uninstall them all

    sudo gem uninstall cocoapods cocoapods-core cocoapods-deintegrate cocoapods-downloader cocoapods-plugins cocoapods-search cocoapods-trunk cocoapods-try


    # brew uninstall any version of ruby, rbenv, or ruby-build that is installed. You might have to use

    brew uninstall ruby --force


    # Reinstall ffi and cocoapods with x86

    sudo arch -x86_64 gem install ffi
    sudo arch -x86_64 gem install cocoapods


    # To check this install before using fastlane to bootstrap the application, navigate to the ios folder within the app and then run `pod install` to confirm

Source: [Installing cocoapods for M1](https://stackoverflow.com/questions/66644365/cocoapods-on-m1-apple-silicon-fails-with-ffi-wrong-architecture/66771694#66771694)
