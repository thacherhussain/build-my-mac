# Build My Mac

Do yourself a favor and don't skip touch ID in the initial setup

To use your computer comfortably during setup:

- trackpad > turn on tap to click
- update the dock placement and show/hide dock
- remove all permanent dock items
- change the desktop background to something nice

Recommended: change your password to something super simple JUST FOR SETUP and then change it to something more secure afterwards

- Setup internet
- Sign into your apple account in system preferences
- Add at least your personal email to the Internet Accounts in System Preferences

IMPORTANT: Make sure that your operating systems is up to date

## Xcode

Start the XCode download from the AppStore

Open XCode to see/accept any additional requirements or install any additional components

If they're not installed by Homebrew, you can install the XCode Command Line Tools from terminal by running:

```
xcode-select --install
```

If needed you can also accept the Xcode agreement from the terminal by running:

```
sudo xcodebuild -license accept
```

## Homebrew

From Terminal install Homebrew:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Make your life easier and immediately install a few basics and some nice to haves...

```
brew install git python yarn watchman
```

\*yarn requires node, but don't worry about that quite yet

```
brew install --cask spectacle iterm2 obsidian firefox 1password visual-studio-code
```

## Setting stuff up to set stuff up

- open spectacle
- open and setup 1Password, change shortcut to `cmd + .`
- add/login into Accounts — at least personal gmail
- open and setup Firefox and/or log into Firefox Sync
- open VScode, login to sync settings
- quit terminal and open iTerm2
- open Obsidian and link to iCloud vault

## iTerm2 / oh-my-zsh

Install oh-my-zsh:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Add powerlevel10k theme: https://github.com/romkatv/powerlevel10k

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

## Node via nvm OR asdf

If you're going to use asdf for other project it's a bit of a headache to also have nvm installed, there is support for legacy version files, but it especially with issues already present with M1 it's easier to pick one or the other.

### nvm

```
brew install nvm
```

- Follow the directions provided after the install and don't forget to run `source ~/.zshrc` to apply those changes
- Verify that this has worked by running `nvm ls-remote 16` which will list all available versions of node v16
- Check out the [node docs](https://nodejs.org/en/about/releases/) to decide which version(s) of node you would like to install and then run `nvm install 00 --lts` which will install the latest stable version for that version node.
- To see your current config run `nvm list`
- For more options and config run `nvm -h`
- In any terminal if you want to see which version of node you are using run `node -v`.

### asdf

[asdf commands docs](https://asdf-vm.com/manage/commands.html)

Install dependencies:

```
brew install coreutils curl git gpg gawk
```

Starting with the basics -- ruby, node, java and yarn. With M1 you will most likely have to use the `arch -x86_64` prefix, ex.

```
arch -x86_64 asdf install nodejs latest
```

```
arch -x86_64 asdf install java openjdk-14
```

```
asdf install yarn
```

If you are using ruby exports in your .zshrc file, make sure that your asdf call is above any ruby exports

If you're having trouble with ruby checkout [M1 troubleshooting](#m1-troubleshooting)

## Git Configuration

Configure Git in the Terminal to sign your commits with your name and email address.

**WARNING:** Before running the following commands, replace `YOUR FULL NAME` and `YOUR EMAIL ADDRESS` with the name and email from [your GitHub account](https://github.com/settings/profile).

```
git config --global user.name 'YOUR FULL NAME'
git config --global user.email 'YOUR EMAIL ADDRESS'
```

run `git config --list` to check that you set these correctly

[Setting up GitHub SSH keys](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)

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
brew install --cask rocket alfred rescuetime textexpander keyboard-maestro setapp spotify expressvpn sourcetree react-native-debugger
```

If you want to do all this in one go...

```
brew install --cask slack google-drive google-chrome zoom karabiner-elements rocket alfred rescuetime textexpander keyboard-maestro setapp spotify expressvpn sourcetree react-native-debugger
```

If you have a touch bar

```
brew install pock
```

Then run

```
brew cleanup -s
```

## React Native

Install expo-cli:

```
yarn global add expo-cli
```

## Install Mac Apps with Homebrew "mas"

[mas](https://github.com/mas-cli/mas) is a command line interface installed with homebrew to install mac app store applications

```
brew install mas
```

Find an app to install:

`mas search Spark` returns a list of possible matches with codes

`mas install 1176895641`

Spark: `mas install 1176895641`

Notability: `mas install 736189492`

Bear: `mas install 1091189122`

Deliveries: `mas install 290986013`

Moom: `mas install 419330170`

TestFlight: `mas install 899247664`

All together now:

```
mas install 1176895641 736189492 1091189122 290986013 419330170 899247664
```

Seems like you actually have to download these from the sites...

[postgres app](https://postgresapp.com/)

[devonthink 3](https://www.devontechnologies.com)

Then run

```
brew cleanup -s
```

### More Installations and Configs

- Finder > View > Show Path Bar
- Activate other Internet Accounts
- Check Allowed Notifications
- Slack Teams
- Keyboard Maestro - link with cloud config file
- Setapp - sign in and download favorited apps and config
- Alfred
  - restore from previous config
  - Keyboard > Turn off Apple Spotlight, change cmd + space to Alfred
- Turn Off Guest User
- Update Key Repeat from terminal

```
defaults write -g ApplePressAndHoldEnabled -bool false
```

If needed, install MS Office Separately because it requires confirmation with a pop-up

```
brew install microsoft-office
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
