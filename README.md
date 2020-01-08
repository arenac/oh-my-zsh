# oh-my-zsh
Setup for ohmyzsh

## Before start on Windows, it's required to enable "Windows subsystem for Linux and install a Linux system 

* Open PowerShell and type

```Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux```

* Accept the change and restart the OS
* Install Windows Subsystem for Linux (you can use another package manager other than Chocolatey)

```choco install wsl-ubuntu-1804```

* Afer install it, do the next steps using the Ubunto terminal

## Ohmyzsh installation and customization

* Install it through curl [zsh](https://github.com/ohmyzsh/ohmyzsh)
* Theme installation [spaceship](https://github.com/denysdovhan/spaceship-prompt)
* Open the .zshrc file ```code ~/.zshrc```
* Change the ZSH_THEME to "spaceship"
* In the end of the .zshrc file add he following lines

```
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)

SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "
```

* Install [zplugin](https://github.com/zdharma/zplugin#installation)
* After zplugin installation, the .zshrc file should have this lines added automatically in the end

```
### Added by Zplugin's installer
source "$HOME/.zplugin/bin/zplugin.zsh"
autoload -Uz _zplugin
(( ${+_comps} )) && _comps[zplugin]=_zplugin
### End of Zplugin installer's chunk
```

* To install plugins through zplugin, add the pluglin in the end of the file .zshrc following the sintaxy

```
zplugin light zsh-users/zsh-autosuggestions
zplugin light zsh-users/zsh-completions
zplugin light zdharma/fast-syntax-highlighting
```

## Aditional Comments

The Ubunto app installed runs zsh but the icon feature doesn't work well on Windows. The good news is if you are a VS Code user, the icons work well. The only requirement is to install the Remote - WSL plugin and set the WSL bash as default in VS Code.

**If you need to use a bash command other than the Ubunto app default, you need to install your application inside the Ubunto app, for example NodeJS which is not installed by default. Lastly, you can also update and upgrade almost every app installed inside Ubunto app.**
