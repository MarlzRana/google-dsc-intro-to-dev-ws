# Instructions

## Installing WSL on the Windows System

- Open **Terminal**
- Set **Windows Terminal** as your default terminal and save changes
- Run <code>wsl --install</code> (in a multi-user environment use command <code>wsl --install -d Ubuntu</code>)
- Wait for WSL to install
- Enter a new Unix username <i>(Ideally it should be as short as possible to make things easier)</i>
- Create a password <i>(Ideally short as you will need to type this out every time you want to perform an admin operation)</i>
- Set your default profile within **Windows Terminal** to **Ubuntu**
- Now every time you open **Windows Terminal** you should be within your Linux sub-system
- Now update everything by running
  - <code>sudo apt-get update</code> which tells the unix to get a list of all packages <i>(we'll come onto the notion of packages later) that need updating and store that list locally</i>
  - <code>sudo apt-get upgrade</code> tells unix then go ahead and upgrade those fetched changes
- Now **restart the shell**
- Set **Linux as your default profile** and save changes

## Unix Commands

- <code>pwd</code>: See your current working path
- <code>ls</code>: See files and directories within the current directory (introduce the idea of flags such as <code>-a</code> to tell <code>ls</code> you want to list all files including hidden files and directory's)
- <code>cd</code>: change directory
- <code>mkdir</code>: make directory
- <code>rmdir</code>: remove director
- <code>touch</code>: new file
- <code>sudo</code>: admin mode

## Install a custom Unix package manager

- Run the command <code>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"</code>
- Enter your password
- Hit enter
- Give it some time to install
- **It should recommend you some commands to run, run them in a separate terminal window**
- Here you should be able to see how many steps of installation Homebrew is taking care of, making the installation of packages more of a one-command process

## Switch bash to zsh

- Run the command <code>sudo apt-get install zsh</code>

  #### Windows Only:

  - Note zsh won't show up till we install oh-my-zsh which asks us if we would like to set our main shell to zsh

## Oh-my-zsh

- Run <code>sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"</code>

  #### Windows Only:

  - Then type <code>y</code> to set zsh as your default terminal
  - Then confirm the action with your password
  - Now zshell should be configured with oh-my-zsh managing it

## VSCode

### Technical

- Go to <code>https://code.visualstudio.com/download</code>
- Press download
- Agree to the agreement
- Press yes twice
- **Enable options to open with code** <i>(Windows only)</i>
- Press next then install
- I would recommend creating a GitHub account and then immediately signing in to enable settings sync
- Then I would **install the WSL extension** <i>(Windows only)</i>
- Restart your terminal
  #### MacOS
  - Open VSCode
  - Press Command + Shift + P
  - Type shell command
  - Click on install code command in path

## Nerd Font

- Join our Discord server
- Install the font I have attached

  #### Windows

  - Open settings.json of Windows Terminal
  - Set the font face of your Linux terminal to "CascadiaCove NF"
  - <code>"font":{"face": "CaskaydiaCove NF"}</code>

  #### Mac

  - Make sure the terminal is open and selected (it's your currently active window)
  - In the top left of your menu bar (the bar at the top) click on Terminal > Preferences
  - Click Profiles
  - Change the font to CaskaydiaCoveNF
  - Then close all windows

## PowerLevel10K

- Run the command <code>git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k</code>
- Run the command <code>code ~/.zshrc</code>
- Set <code>ZSH_THEME="powerlevel10k/powerlevel10k"</code> in ./zshrc
- Run <code>exec zsh</code> to restart the shell
- Then the p10k wizard should launch on your next instance of launching the terminal
- Then type y or n where appropriate depending on whether you can see the glyph described clearly or not
- Then make custom choices from there onwards (Make sure to indicate this can be whatever you want)
- Ensure to choose Unicode
- Do not enable the transient prompt
- Then make sure to select verbose where appropriate

## Zsh Plugins

- Run <code>cd ~/.oh-my-zsh/plugins</code>
- Run <code>git clone https://github.com/zsh-users/zsh-syntax-highlighting.git</code>
- Run <code>echo "source \${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> \${ZDOTDIR:-$HOME}/.zshrc</code>
- Run <code>git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions</code>
- Run <code>cd ~ </code>
- Run <code>code .zshrc</code>
- Add <code>zsh-autosuggestions</code> to zsh plugins in .zshrc with a space don't use a comma
  #### MacOS
  - Run <code>`touch ~/.hushlogin`</code>
  - Restart terminal

## Asdf

- Run <code>brew install asdf</code>
- Per language, we need to install a language plugin which essentially manages that programming language
- Let's try installing Python:
  - Run <code>asdf plugin add python</code> to add the python language manager
  - Run <code>asdf install python latest</code>
  - Run <code>asdf install python latest</code> (
- Want to work with NodeJS?
  - Run <code>asdf plugin add nodejs</code>
  - Run <code>asdf install nodejs latest</code>
- Want to use NodeJS long-term support version?
  - Run <code>asdf install nodejs lts</code>
  - Run <code>asdf list nodejs</code> <i>This shows us our versions of NodeJs installed</i>
  - Run <code>asdf global nodejs lts </code><i> If you want to switch to the lts version</i>
- Want to use an older version of Python?
  - Run <code>asdf install python 3.8.0</code>
  - Run <code>asdf list python</code><i>This shows us our versions of Python installed</i>
  - Run <code>asdf global python 3.8.0</code><i> If you want to switch to Python version 3.8.0</i>
