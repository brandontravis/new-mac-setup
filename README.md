# New Mac Setup
OS X Development Environment

These repo is designed to rapidly setup new Mac OS X development environements. It is heavily based on Mathias and Paul Irish dotfiles, with a few specific modifications.

## Preinstallation / Prerequisites

1. Install Mac OS X
2. Update OS X (Menu > Software Update)
3. Copy Backup Files (If necessary)
4. Download the following applications manually (used during the rest of setup)
    - iTerm 2
    - Dropbox
    - Office 365 (Dropbox)
    - MAMP Pro (Dropbox)
5. Let Dropbox Sync (alternatively, download a zip of the new-mac-setup project)
    on GitHub [https://github.com/brandontravis/new-mac-setup])
6. Create a Symlink to the sh-scripts directory (note, everything in this directory *should* be `chmod u+x ...`, but set those permissions if they don't run for some reason)

    ```
    ln -s ~/Dropbox\ \(Personal\)/Work/Development/Projects/new-mac-setup/sh-scripts ~
    OR
    ln -s ~/Downloads/new-mac-setup-master/sh-scripts ~
    ```

7. Add the sh-scripts directory to $PATH (Will add to ZSH profile later, if needed)

    ```
    echo 'export PATH="$PATH:/Users/brandontravis/sh-scripts"' >> ~/.bash_profile
    source ~/.bash_profile # May not be necessary
    ```

## Begin Script Installation
1. Run `.installconfig` to install and configure
    - OS X Command Line Tools
    - Homebrew
    - Node
    - Git
    - Brew Caskroom
    - Oh My ZSH
    - Grunt
    - Yeoman
    - Bower
    - Sass
2. Restart and configure iTerm 2
    - Install Source Code Pro font in Fontbook (new-mac-setup/required-files/source-code-pro.zip)
    - iTerm 2 -> General
        - Uncheck 'Confirm "Quit iTerm 2"'
        - Uncheck 'Confirm closing multiple sessions'
    - iTerm 2 -> Appearance
        - Uncheck 'Hide tab bar when there is only one tab'
    - iTerm 2 -> Profiles -> Colors
        - Load Presets -> cobalt-theme-iTerm2 (new-mac-setup/required-files/cobalt-iterm-master.zip)
    - iTerm 2 -> Profiles -> Text
        - Change both Regular and Non-ASCII Fon'ts to 10pt Source Code Pro
    - iTerm 2 -> Profiles -> Window
        - Change transparency to about 80%
3. Add `.bash_profile` to zsh path (this should be required, but weird stuff happens when I don't do this)
    ```
    echo 'source ~/.bash_profile'
    ```
3. Run `.caskfile`
4. Install from App Store
    - Dash 3 (Purchased through App Store)
    - Logitech Camera Settings
    - Any.do (Purchased through App Store)
    - Microsoft Remote Desktop
    - MiniPlayer
    - Growl
    - StuffIt Expander
    - Twitter
5. Install Creative Cloud (/opt/homebrew-cask/caskroom/adobe-creative-cloud)
    - Adobe Illustrator
    - Adobe Photoshop
    - Adobe InDesign
    - Adobe UX
6. Install Parallels & Configure VMs as necessary
7. Restart Mac OS X

## Setup and Configure Sublime Text 3 to use Dropbox Files
1. Remove Local Folders
    ```
    rm -rf ~/Library/Application\ Support/Sublime\ Text\ 3/Packages
    rm -rf ~/Library/Application\ Support/Sublime\ Text\ 3/Installed\ Packages
    ```
2. Symlink files to Dropbox
    ```
    ln -s ~/Dropbox\ \(Personal\)/Work/Development/Projects/new-mac-setup/required-files/Sublime\ Text\ 3/Packages ~/Library/Application\ Support/Sublime\ Text\ 3
    ln -s ~/Dropbox\ \(Personal\)/Work/Development/Projects/new-mac-setup/required-files/Sublime\ Text\ 3/Installed\ Packages ~/Library/Application\ Support/Sublime\ Text\ 3
    ```

## Setup and Confiure MAMP to use Dropbox DB Instead of Local DB
1. Run MAMP once and exit
2. Remove Local MAMP databases
    ```
    rm -rf /Library/Application\ Support/appsolute/MAMP\ PRO/db/mysql
    ```
3. Symlink Dropbox Databases to MAMP
    ```
    ln -s ~/Dropbox\ \(Personal\)/Work/Development/Databases/mysql /Library/Application\ Support/appsolute/MAMP\ PRO/db
    ```
4. Link Dropbox Hosts File (Not Yet)

## Run .osx dotfile
1. Run `.osx`
2. Restart machine

## Create Aliases
1. Symlink Aliases File
    ```
    ln -s ~/Dropbox\ \(Personal\)/Work/Development/Projects/new-mac-setup/sh-scripts/.aliases ~
    echo 'source $HOME/.aliases' >> ~/.zshrc
    ```

## Cleanup / Postinstall
1. Add licenses codes to all apps, setup dock, and configure necessary / additional preferences
2. Install Alfred Workflows
3. Open Dash to initialize, then close it. Link Dash docsets
    ```
    rm -rf ~/Library/Application\ Support/Dash/DocSets
    rm -rf ~/Library/Application\ Support/Dash/library.dash
    ln -s /Users/brandontravis/Dropbox\ \(Personal\)/Work/Development/Projects/new-mac-setup/required-files/Dash/DocSets /Users/brandontravis/Library/Application\ Support/Dash
    ```
## ToDo
1. Link Dash DocSets
2. Add Sketch to Caskfile
3. New Sublimetext settings script
4. Include all other settings for misc apps
5. Link to Hosts file
6. Alfred Workflows
7. Brewfile
