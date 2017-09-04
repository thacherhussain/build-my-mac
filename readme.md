# 🔧 Welcome to My Mac-Maker 💻

This is, yet another, dev environment start-up script.
My goal here is to break down the particular items being installed into individual modules.
Each module is then sourced from the main *install.sh* script with `source ./run/[MODULE]/setup`.
This makes it real easy to remove anything you do not want without worry of breaking other parts of this build.
Likewise, this structure lends itself to being extended with any modules of your own.

<hr>

## Project Organization

The *install.sh* script is what will be run upon executing the start-up command listed below.
This script will get Brew up and running on your machine 🍻.
The Brewfile will install a number of binarys, libraries and applications durring the Brew install process.
It is recommended that you look over this file and the supporting *brew-casks* and *brew-mas* files to customize the setup to your liking. Any applications that are paid apps must be purchased with the apple id you are using before running the script.
Note that Xcode is one of the items included in the `mas` bundle.
It has been isolated to its own *xcode-install* file as a convenience to allow for an optional install durring run time,
due to its hell-ishly long install times ⏰.

After the Brew process is finished the *install.sh* script will begin to source the individual system modules to be installed.
If you do not wish to have a particular module installed on your machine simply delete,
or comment out, the line in the *install.sh* script where it is sourced.

All modules are organized together in the **run** 📂.
In each of their respective directories lives a *setup* script, which is what is sourced in the main *install.sh* script.
Some of the individual modules have additional dotfiles or supporting scripts files.
These may be files that will be symlinked into your **HOME** 📂,
provided as alternative install options, further modularization, or organizational purposes.
For example in the *zsh* module both *antigen* (my personal preference) and *oh-my-zsh* are included (pick your ☠).

<hr>

## Install Instructions

### 💾 Download...

Run the following commands:

```sh
curl -L https://api.github.com/repos/thacherT1D/mac-maker/tarball --create-dirs -o ~/Projects/dotfiles.tar.gz
```

Pulls down tar file of this repo onto your machine while creating a */Projects* directory.

```sh
tar -zxvf ~/Projects/dotfiles.tar.gz -C ~/Projects/
```

Moves into */Projects* directory and untars the tar downlaoded file.

```sh
cd ~/Projects && mv thacherT1D* dotfiles
```

Changes the name of the untared directory from "MrJadaml-mac-maker-[SHA]" to "dotfiles"

### ❄️ Personalize...

Once the project is copied I suggest you rummage through it and make any modifications to suit your personal preferences.

There is an optional Brew mas setup for Apple Store apps that you will be prompted about durring installation.
Please have your email and password for the Apple Store ready.

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

#### Accept Xcode Agreement

To accept the Xcode agreement from the terminal, run the following command in your terminal:

```
sudo xcodebuild -license accept
```

##### Powerline fonts config

In iTerm, move to the Text options by selecting iTerm2 > Preferences > Profile > Text
In the Text preferences pane, enable the "Use a different font for non-ASCII text" option.
Then change the font to one of Powerline options. 13pt Cousine is a good choice.

⚠️ Note: Some of the settings require the system to be logged out and back in before taking effect.

<hr>

## The Manifest 📕

#### Javascript

- [node] - A JavaScript runtime built on Chrome's V8 JavaScript engine.
- [nvm] - Node Version Manager: Simple bash script to manage multiple versions of node.

[node]: https://nodejs.org/en/
[nvm]: https://github.com/creationix/nvm

#### Python

- [Python 3] - An interpreted, object-oriented, high-level programming language.
- [Pyenv] - Simple Python version management.
- [Virtualenvwrapper] - Wrappers for creating virtual environments and isolating dependencies.

[Python 3]: https://www.python.org/download/releases/3.0/
[Pyenv]: https://github.com/yyuu/pyenv
[Virtualenvwrapper]: https://virtualenvwrapper.readthedocs.io/en/latest/

#### Ruby

- [Ruby] - A dynamic, open source programming language with a focus on simplicity and productivity -- MINASWAN
- [rvm] - Ruby Version Manager: Simple script to mange multiple versions of Ruby.

[Ruby]: https://www.ruby-lang.org/en/
[rvm]: https://rvm.io/

#### Homebrew

- [Homebrew] - Homebrew installs the stuff you need that Apple didn’t.
- [ctags] - Indexes language objects in source files so your text editor can quickly reference them.
- [git] - Open source version control system | update.
- [git-secrets] - Prevents you from committing secrets and creds into git repositories.
- [heroku-toolbelt] - A Heroku CLI.
- [httpie] - Command line HTTP client with an intuitive UI, JSON support, syntax highlighting.
- [mas] - Mac App Store command line interface.
- [postgresql] - An open source relational database management system (DBMS).
- [mySQL]
- [vim] - Highly configurable text editor built in with most UNIX systems | update.
- [z] - A more convenient `cd` which tracks your most used directories, based on 'frecency'.

<!-- [Homebrew]: http://brew.sh/
[ctags]: http://ctags.sourceforge.net/
[git]: https://git-scm.com/
[git-secrets]: https://github.com/awslabs/git-secrets
[heroku-toolbelt]: https://devcenter.heroku.com/articles/heroku-cli
[httpie]: https://httpie.org/
[mas]: https://github.com/mas-cli/mas
[postgresql]: https://www.postgresql.org/
[mySQL]
[vim]: http://www.vim.org/
[z]: https://github.com/rupa/z -->

#### Shell

- [antigen] - A plugin manager for zsh, inspired by oh-my-zsh and vundle.
- [bash] - Built-in shell | update.
- [oh-my-zsh] - Community-driven framework for managing your zsh configuration.
- [zsh] - An interactive UNIX shell.

[antigen]: https://github.com/zsh-users/antigen
[bash]: https://www.gnu.org/software/bash/
[oh-my-zsh]: https://github.com/robbyrussell/oh-my-zsh
[zsh]: http://www.zsh.org/

#### Apps - Homebrew Cask
- [java]
- [Atom] - GitHub's open source text editor
- [Alfred] - Mac Spotlight replacement with more custom and productive actions to control your Mac.
- [Bartender]
- [Duet]
- [Firefox] - Mozilla's web browser.
- [Firefox Developer Edition]
- [Google chrome] - Google's web browser.
- [Google Drive]
- [iterm2] - A terminal emulator and replacement for Mac's default Terminal app.
- [JetBrains Toolbox]
- [Join.me]
- [jumpcut]
- [MailButler]
- [Minecraft]
- [Microsoft Office]
- [mySQL Workbench]
- [Screenhero] - Coding oriented screen share with multi mouse/cursor.
- [Slack] - A messaging app (corporate IRC 👔).
- [Spectacle]
- [Spotify]
- [Sketch]
- [Skype]

<!-- [Atom]: https://atom.io/
[Alfred]: https://www.alfredapp.com/
[Firefox]: https://www.mozilla.org/en-US/firefox/products/
[Firefox Developer Edition]
[Google chrome]: https://www.google.com/chrome/
[Mail Butler](https://www.mailbutler.io)
[iterm2]: https://www.iterm2.com/
[Screenhero]: https://screenhero.com/
[Slack]: https://slack.com/ -->

#### App Store - Homebrew Mas

- [Evernote] - Note manager app.
- [Pocket] - Article saver/offline reader.
- [Sip] - Color picker.
- [Tweetbot]
- [Xcode] - Integrated dev environment with tools for developing for macOS, iOS, WatchOS and tvOS.

*If you are going to test this out a few times it is recommended that you download the dmg for Xcode and preinstall it from a usb drive rather than having to download it each time*

<!-- [Evernote]: https://evernote.com/
[Pocket]: https://getpocket.com/
[Sip]: http://sipapp.io/
[Tweetbot]
[Xcode]: https://developer.apple.com/xcode/ -->

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

#### My "After-Market" Adds

For Java Environment:

- Install [MySQL Community Server](https://dev.mysql.com/downloads/mysql/)
- [Java8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
- [Gradle](http://www.gradle.org/): *Add to brew packages
  - Run `brew install gradle`
  - To confirm, run `gradle -version`. The computer should display `Gradle 2.XX`.


#### My Post Install Configs
- Dock Icons and Order
- Items to load on startup
- Desktop image (photos)

Other applications:
- diasend
- Craft Manager

- zsh theme: cobalt2 (https://github.com/wesbos/Cobalt2-iterm) + powerline font (https://github.com/powerline/fonts)

atom plugins:
atom-beautify
atom-bootstrap3
atom-javascript-snippets
auto-indent
*intentions
*javascript-snippets
language-babel
less-autocompile
linter
linter-ui-default
open-in-browsers

autosave on focus

chrome extensions
chrome logins
add all accounts to "Internet Accounts"
