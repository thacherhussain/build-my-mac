# Build My Mac

Dev environment start-up script - born from [MrJadaml's mac-maker](https://github.com/MrJadaml/mac-maker)
My goal here is to break down the particular items being installed into individual modules.
Each module is then sourced from the main *install.sh* script with `source ./run/[MODULE]/setup`.
This makes it real easy to remove anything you do not want without worry of breaking other parts of this build.
Likewise, this structure lends itself to being extended with any modules of your own.

<hr>

## Organization

The *install.sh* script is what will be run upon executing the start-up command listed below.
This script will get Brew up and running on your machine.
The Brewfile will install a number of binarys, libraries and applications during the Brew install process.
It is recommended that you look over this file and the supporting *brew-casks* and *brew-mas* files to customize the setup to your liking. Any applications that are paid apps must be purchased with the apple id you are using before running the script.
Note that Xcode is one of the items included in the `mas` bundle.
It has been isolated to its own *xcode-install* file as a convenience to allow for an optional install durring run time,
due to its hell-ishly long install times.

After the Brew process is finished the *install.sh* script will begin to source the individual system modules to be installed.
If you do not wish to have a particular module installed on your machine simply delete,
or comment out, the line in the *install.sh* script where it is sourced.

All modules are organized together in the **run** file.
In each of their respective directories lives a *setup* script, which is what is sourced in the main *install.sh* script.
Some of the individual modules have additional dotfiles or supporting scripts files.
These may be files that will be symlinked into your **HOME** file, provided as alternative install options, further modularization, or organizational purposes.

<hr>

#### Quick Reformating Guide. 💾

Obviously, back up all the files you don't want to have blown away before going through this process.

- Restart your computer and hold down `⌘ + r`.
- Once you see the white  logo and a progress bar you can let go of `⌘ + r`
- The "macOS Utilities" menu will pop up. Select the "Disk Utility" option from the list.
- From the sidebar labeled "Internal" click on sub hardrive icon labeled "Macintosh HD"
- From the row of icons at the top, click "Erase"
- A popup menu will appear with a field for the "Name" and "Format".
  Just leave the defaults and click the "Erase" button in the bottom right.
- Once it goes through its speel, click "Done"
- Close the Disk Utility window to get back to the "macOS Utilities" window.
- Now choose the option in the list labeled "Reinstall macOS" and click "Continue"
- From here it will guide you through the steps to a fresh install.

**Update the trackpad to use single tap to click**

#### Update Operating System

Go to App Store and run any operating system updates

#### XCode

Install XCode from the AppStore

Install XCode Command Line Tools from terminal: `xcode-select --install`

Accept the Xcode agreement from the terminal: `xcodebuild -license accept`

Open XCode to see/accept any additional requirements or install any additional components


## Install Instructions

### 💾 Download...

Run the following commands:

```sh
curl -L https://api.github.com/repos/thacherT1D/build-my-mac/tarball --create-dirs -o ~/Projects/dotfiles.tar.gz
```

Pulls down tar file of this repo onto your machine while creating a */Projects* directory.

```sh
tar -zxvf ~/Projects/dotfiles.tar.gz -C ~/Projects/
```

Moves into */Projects* directory and untars the tar downloaded file.

```sh
cd ~/Projects && mv thacherT1D* dotfiles
```

Changes the name of the untared directory from "thacherT1D-build-my-mac-[SHA]" to "dotfiles"



### 📝 Install...

Be sure you are in the *dotfiles* directory.

```
cd ~/Projects/dotfiles
```

Then run the following command into your terminal:

```
source install.sh
```

When it promts you to enter your password, be sure to check if it is asking for your computer password or your appleID password.


##### Powerline fonts config

In iTerm, move to the Text options by selecting iTerm2 > Preferences > Profile > Text
In the Text preferences pane, enable the "Use a different font for non-ASCII text" option.
Then change the font to one of Powerline options. 13pt Cousine is a good choice.

⚠️ Note: Some of the settings require the system to be logged out and back in before taking effect.

<hr>

## The Manifest

#### Javascript

- [node](https://nodejs.org/en/) - A JavaScript runtime built on Chrome's V8 JavaScript engine.
- [nvm](https://github.com/creationix/nvm) - Node Version Manager: Simple bash script to manage multiple versions of node.

#### Python

- [Python 3](https://www.python.org/download/releases/3.0/) - An interpreted, object-oriented, high-level programming language.
- [Pyenv](https://github.com/yyuu/pyenv) - Simple Python version management.
- [Virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/) - Wrappers for creating virtual environments and isolating dependencies.

#### Ruby

- [Ruby](https://www.ruby-lang.org/en/) - A dynamic, open source programming language with a focus on simplicity and productivity -- MINASWAN
- [rvm](https://rvm.io/) - Ruby Version Manager: Simple script to mange multiple versions of Ruby.

#### Homebrew

- [Homebrew](http://brew.sh/) - Homebrew installs the stuff you need that Apple didn’t.
- [git](https://git-scm.com/) - Open source version control system | update.
- [git-secrets](https://github.com/awslabs/git-secrets) - Prevents you from committing secrets and creds into git repositories.
- [gradle](http://www.gradle.org/)
- [heroku-toolbelt](https://devcenter.heroku.com/articles/heroku-cli) - A Heroku CLI.
- [mas](https://github.com/mas-cli/mas) - Mac App Store command line interface.
- [postgresql](https://www.postgresql.org/) - An open source relational database management system (DBMS).
- [mySQL](https://www.mysql.com/) - Another popular open source database  
- [z](https://github.com/rupa/z) - A more convenient `cd` which tracks your most used directories, based on 'frecency'.
- [vim](http://www.vim.org/)

#### Shell

- [bash](https://www.gnu.org/software/bash/) - Built-in shell | update.
- [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) - Community-driven framework for managing your zsh configuration.
- [zsh](http://www.zsh.org/) - An interactive UNIX shell.

#### Apps - Homebrew Cask
- [Atom](https://atom.io/) - GitHub's open source text editor
- [Alfred](https://www.alfredapp.com/) - Mac Spotlight replacement with more custom and productive actions to control your Mac.
- [Bartender](https://www.macbartender.com/)
- [Duet](https://www.duetdisplay.com/)
- [Firefox](https://www.mozilla.org/en-US/firefox/products/) - Mozilla's web browser.
- [Firefox Developer Edition]
- [Google chrome](https://www.google.com/chrome/) - Google's web browser.
- [Google Drive](https://www.google.com/drive/download/)
- [iterm2](https://www.iterm2.com/) - A terminal emulator and replacement for Mac's default Terminal app.
- [Java 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [JetBrains Toolbox](https://www.jetbrains.com/toolbox/)
- [Join.me](http://join.me)
- [jumpcut](http://jumpcut.sourceforge.net/)
- [MailButler](https://www.mailbutler.io)
- [Minecraft](https://minecraft.net/en-us/)
- [Microsoft Office](https://www.microsoft.com/en-us/store/b/office?icid=CNavSoftwareOffice&activetab=tab%3ahomeorpersonal)
- [mySQL Workbench](https://www.mysql.com/products/workbench/)
- [Slack](https://slack.com/) - A messaging app
- [Spectacle](https://www.spectacleapp.com/)
- [Spotify](http://spotify.com)
- [Sketch](sketchapp.com)
- [Skype](http://www.skype.com)

#### App Store - Homebrew Mas

- [Evernote](https://evernote.com/) - Note manager app.
- [Pocket](https://getpocket.com/) - Article saver/offline reader.
- [Sip](http://sipapp.io/) - Color picker.
- [Xcode](https://developer.apple.com/xcode/)- Integrated dev environment with tools for developing for macOS, iOS, WatchOS and tvOS.

*If you are going to test this out a few times it is recommended that you download the dmg for Xcode and preinstall it from a usb drive rather than having to download it each time*

#### My "After-Market" Adds
For Java Environment:
- Install [MySQL Community Server](https://dev.mysql.com/downloads/mysql/)

#### Next Planned Additions
- React Build Tools
- Android Studio Configuration

<hr>

##### Notes from Last Run: 
- Hombrew Link Failure
- Adjust order or placement Brewfile or Brew Cask for Java8 in order to have it install before gradle
- Python version failure
- Use of Pip command failure
- OSX time machine settings commented out
Change to mine:
- dock size
- highlight color
- key repeat speed

#### My Post Install Configs
- Dock Icons and Order
- Startup Items
- All Accounts
- Slack Teams
- Desktop image
- update trackpad to include single click

- Sketch Craft Manager
- Sketch Plugins: 
  - Diverse UI
  - Anima Launchpad

zsh theme: cobalt2 (https://github.com/wesbos/Cobalt2-iterm) + powerline font (https://github.com/powerline/fonts)

Atom plugins:
- atom-beautify
- atom-bootstrap3
- atom-javascript-snippets
- auto-indent
- open-in-browsers
- autosave on focus

Chrome logins and extensions
