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
