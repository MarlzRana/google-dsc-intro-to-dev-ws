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

## Any questions?

## Unix Commands

**Motivation**

- **Go back to PowerPoint**
- Now that we are all on a Unix-based operating system I am going to introduce you to a couple of basic Unix commands
- These commands help will help you navigate around in the Unix file system
- **Go through each command one by one**:
  - <code>pwd</code>: See your current working path
  - <code>ls</code>: See files and directories within the current directory (introduce the idea of flags such as <code>-a</code> to tell <code>ls</code> you want to list all files including hidden files and directory's)
  - <code>cd</code>: change directory
  - <code>mkdir</code>: make directory
  - <code>rmdir</code>: remove director
  - <code>touch</code>: new file
  - <code>sudo</code>: admin mode

## Any questions?

## Install a custom Unix package manager

### Motivation

- In Unix-based operating systems **all pieces of software are essentially "packages"** which is all the code and data an application would need bundled up
- Unix provides us with a default package manager to manage packages however **there are superior package managers that exist**
- We will be using **HomeBrew** as an alternative package manager as it makes the process of installing and uninstalling packages a lot more clear-cut and easier in comparison to the default package manager

### Technical

- Run the command <code>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"</code>
- Enter your password
- Hit enter
- Give it some time to install
- **It should recommend you some commands to run, run them in a separate terminal window**
- Here you should be able to see how many steps of installation Homebrew is taking care of, making the installation of packages more of a one-command process

## Any questions?

## Switch bash to zsh

### Motivation

- Typically most distributions use a bash shell which is the thing that you use to interact with your computer via commands (i.e this thing in the terminal)
- We are going to be switching our shell from bash to zshell as zshell offers us a greater level of customization
- Mac users typically do not have to switch from zsh to bash as that is now the default shell for Mac users on the latest version of macOS
- The way you can check this is by typing into the command line:
  - <code>which zsh</code>
  - The following line of code should return a file path and if you don't see one you don't have zsh configured on your mac
  - Speak to Billy if you have this issue and he will come around with the quick fix

## Technical

- Run the command <code>sudo apt-get install zsh</code>

## Oh-my-zsh

### Motivation

- Now you won't be able to see zshell yet but we are now going to add oh-my-zsh which is a zshell manager, I know a lot of managers!
- This will help us manage our zshell instance and introduces a whole new array of cool themes and plugins so let's get it installed!

### Technical

- Run <code>sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"</code>

#### Windows Only

- Then type <code>y</code> to set zsh as your default terminal
- Then confirm the action with your password
- Now zshell should be configured with oh-my-zsh managing it

## Any questions?

## VSCode

### Motivation

- VSCode is one of the most popular text editors, meaning that it helps you only write code unlike an integrated IDE which helps you both write code and do code management tasks
- Most people like to use a VSCode instead of an IDE as IDEs are typically made for a specific language whereas a text editor like VSCode supports multiple languages in a single text editor (making it more suitable for projects with multiple languages) and is generally more lightweight making it snappier and faster

### Technical

- Go to <code>https://code.visualstudio.com/download</code>
- Press download
- Agree to the agreement
- Press yes twice
- **Enable options to open with code**
- Press next then install
- I would recommend creating a GitHub account and then immediately signing in to enable settings sync
- Then I would **install the WSL extension**
- Restart your terminal
  #### MacOS
  - Open VSCpde
  - Press CMD + SHIFT + P
  - Type shell command
  - Click on install code command in path

## Any questions?

## Nerd Font

### Motivation

- Next, we going to install a NerdFont
- We are now getting to real customization of the terminal to get it ready for future power use
- I have attached a NerdFont that I like, note that there are a set of them and you can choose any like from <a href="nerdfonts.com">nerdfonts.com</a>
- The reason we have to install a NerdFont in specific and not just some general font, is that so we can get access to glyphs which are icons provided by the font
- These glyphs are going to be used by the next thing we are going to install which is powerlevel10k to display us useful stats within our terminal as we use it hence increasing the terminal's utility

### Technical

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

## Any questions?

## PowerLevel10K

### Motivation

- The terminal so far just lists the directory we are in currently
- What if we could get the terminal to tell us useful information as we navigate through directories?
- Such as the language a project within a directory is coded in or the number of unstaged changes or the current branch name (which we will learn more about once we come to learning Git)?
- That's where PowerLevel10k or p10k comes into play, and provides us useful contextual information when within a directory and allows for further terminal customization

### Technical

- Run the command <code>git clone --depth=1 https://github.com/romkatv/powerlevel10k.git \${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k</code>
- Run the command <code>code ~/.zshrc</code> (Mention that the tilda is shorthand for the home directory)
- Set <code>ZSH_THEME="powerlevel10k/powerlevel10k"</code> in ./zshrc
- Run <code>exec zsh</code> to restart the shell
- Then the p10k wizard should launch on your next instance of launching the terminal
- Then type y or n where appropriate depending on whether you can see the glyph described clearly or not
- Then make custom choices from there onwards (Make sure to indicate this can be whatever you want)
- Ensure to choose Unicode
- Do not enable the transient prompt
- Then make sure to select verbose where appropriate

## Zsh Plugins

### Motivation

- There are further ways we can make our terminal even more useful and that is through
  - Terminal command syntax highlighting (which helps highlight what valid commands are)
  - Command auto-completion (which is as it sounds helps automatically complete commands for you based on command history)

### Technical

- Run <code>cd ~/.oh-my-zsh/plugins</code>
- Run <code>git clone https://github.com/zsh-users/zsh-syntax-highlighting.git</code>
- Run <code>echo "source \${(q-)PWD}/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh" >> \${ZDOTDIR:-$HOME}/.zshrc</code>
- Run <code>git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions</code>
- Run <code>cd ~ </code>
- Run <code>code .zshrc</code>
- Add<code>zsh-autosuggestions</code> to zsh plugins in .zshrc with a space don't use a comma
  #### MacOS
  - Run <code>`touch ~/.hushlogin`</code>
  - Restart terminal

## Asdf

### Motivation

- Installing new programming languages on your machine can be difficult and especially managing multiple versions of them
- asdf is a global language version and allows us to install any programming language (provided someone has a plugin for it) and manage multiple versions easily at the touch of a single command

### Technical

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
