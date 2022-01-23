# Build My Mac

Before getting started make sure that your operating systems is up to date

Make your life easier install [iTerm](https://iterm2.com/), [Firefox](https://www.mozilla.org/en-US/firefox/new/?redirect_source=firefox-com), and [1Password](https://1password.com/downloads/mac/) from the websites

To use your computer comfortably during setup trackpad > turn on tap to click

You can also change your password to something really simple while you're doing the setup to make it easier during setup and then change it back to something safer after


## XCode

Install XCode from the AppStore

Install XCode Command Line Tools from terminal: `xcode-select --install`

Accept the Xcode agreement from the terminal: `sudo xcodebuild -license accept`

Open XCode to see/accept any additional requirements or install any additional components


## Homebrew

Run this command to install Homebrew
```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Install the basics: `brew install git z watchman gradle yarn`


## Git Configuration
Configure Git in the Terminal to sign your commits with your name and email address.

**WARNING:** Before running the following commands, replace `YOUR FULL NAME` and `YOUR EMAIL ADDRESS` with the name and email from [your GitHub account](https://github.com/settings/profile).

```
git config --global user.name 'YOUR FULL NAME'
git config --global user.email 'YOUR EMAIL ADDRESS'
```


## nvm and node

Then we'll use Homebrew to install nvm (a version manager for node) and [node](https://nodejs.org/) which is an open-source, cross-platform runtime system for developing applications in JavaScript. In other words, it runs JavaScript outside the browser.

If you're jumping in here make sure you run `brew update` before running `brew install nvm`

Then create an nvm directory at your root with `mkdir ~/.nvm`

Then open your .zshrc file in vim with `vim ~/.zshrc` 

Then add the following to the .zshrc file
```
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh
```

save and exit out of vim with `ESC + :wq` 

apply these changes to your terminal `source ~/.zshrc`

verify that this has worked by running `nvm ls-remote` which will list all the available versions of node

then run `nvm install node` which will install the latest version of node

You can then use nvm to install whichever version of node that you need, for example if you want to install node 14 you would use `nvm install 14`. To view all versions of node that you have installed `nvm ls`. 

In any terminal if you want to see which version of node you are using run `node -v`. 

nvm is super useful to see what else it can do you can check out the [nvm docs](https://github.com/nvm-sh/nvm)


## Install sdkman to install and manage java versions

Run `curl -s "https://get.sdkman.io" | bash` to install sdkman

Then run `source "$HOME/.sdkman/bin/sdkman-init.sh"`

To confirm the installation run `sdk version` then you should see something like `sdkman 5.13.1`

Then to install java versions `sdk install java xx.xx.x` where `xx.xx.x` is the version number or just `sdk install java` to install the latest version. Install the latest version and a java 8 version. 

Confirm java installation with `java -version`. You can switch back and forth with 

Checkout more about [sdkman](https://sdkman.io/)



## Oh My Zsh
[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

#### .zshrc file config with custom scripts
Add the following and delete anything extraneous

```
ZSH_THEME="af-magic"
plugins=(git node npm macos z)
```


## Install Apps with Homebrew

If you have a touch bar `brew install pock`

Productivity basics `brew install alfred spectacle rescuetime`

`brew install karabiner-elements`
[karabiner-elements](https://karabiner-elements.pqrs.org/docs/getting-started/installation/)

More productivity stuff `brew install textexpander hazel keyboard-maestro`

Developer stuff `brew install visual-studio-code android-studio`

Other stuff `brew install slack google-backup-and-sync google-chrome spotify`

Then run `brew cleanup -s`

#### Setapp -- Install [setapp](https://setapp.com/) -- then download favorited apps


#### Setup Git SSH Keys
[Git Article on setting up SSH Keys](https://help.github.com/articles/connecting-to-github-with-ssh/)




## React Native
Install expo-cli: `yarn global add expo-cli`



### Install Mac Apps with Homebrew "mas"
[mas](https://github.com/mas-cli/mas) is a command line interface installed with homebrew to install mac app store applications 

```brew install mas```

Notability: `mas install 736189492`
Bear: `mas install 1091189122`
Deliveries: `mas install 290986013`

*omnifocus from mac app store because of subscrpition*


To use your computer comfortably during setup:
- Keyboard > Turn off Apple Spotlight, change cmd + space to Alfred
- Turn Off Guest User
- Update Desktop Image
- Trackpad > turn on tap to click

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
- Alfred - restore from previous config


##### And then...

- Update Key Repeat from terminal ```defaults write -g ApplePressAndHoldEnabled -bool false```

If needed, install MS Office Separately because it requires confirmation with a pop-up
`brew install microsoft-office`

If needed, install [zoom](https://zoom.us/)

