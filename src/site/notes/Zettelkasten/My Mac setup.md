---
{"dg-publish":true,"permalink":"/zettelkasten/my-mac-setup/","title":"My Mac Setup","tags":["core/tech","outputs/ideas","status/done"],"created":"2023-01-23T11:06:40.000+00:00"}
---


# Mac Setup

The procedure I follow when cleaning or setting up a new Mac

---
## General setup
### System Settings

### Finder Settings

1. Dock to auto hide
2. Show hidden files
3. Don't show recent applications
4. Configurate Trackpad
### Arc

Arc is the **best browser** that I've ever tried, you can download it on their [website](https://arc.net/).

### 1Password

1Password is my [[Password manager\|Password manager]] and it is available in all platforms and even CLI! You can download it in their [website](https://1password.com/downloads/command-line/)


### Homerow
[Homerow](https://www.homerow.app/) adds [[Vim motions\|Vim motions]] to the whole MacOS allowing you to scroll and click buttons with the keyboard. Can be downloaded from their website

### Karabiner
Is a keyboard customiser for MacOS and I mainly use it to remap my 'Block Mays' to A combination of keys. So I have more hotkeys, you can download it form [their website](https://karabiner-elements.pqrs.org/docs/getting-started/installation/)


### Dotfiles

I've uploaded my dotfiles to Github to save my configurations in different apps. You can download it with. Recommended to do it on your home directory.
```
git clone git@github.com:FeernandoOFF/dotfiles.git
```

### SKHD

SKHD is a [hotkey daemon](https://github.com/koekeishiya/skhd) that it is manly configured to be used along *Yabai*
```
  brew install koekeishiya/formulae/skhd
  skhd --start-service
  
  ln -s ~/dotfiles/skhd/skhdrc ~/.config/skhd/skhdrc
```
### Yabai

Yabai is a tiling window manager for MacOS that allows you to manipulate your app's windows with the keyboard, you can see how I use it on [[Zettelkasten/My Keybindings\|My Keybindings]]

```
brew install koekeishiya/formulae/yabaiw
yabai --start-service
ln -s ~/dotfiles/yabai/yabairc ~/.config/yabai/yabairc
```


---

## Development Setup

#### Homebrew Setup
1. Install Home brew

```
sudo curl -fsSL "https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh" | bash
```

#### Raycast
Raycast is a powerful replacement for the stock spotlight, all the settings are sync in the cloud.

``` 
brew install --cask raycast
```
#### Warp
The terminal that I use is Warp, and the keybindings are stored in the account.
At the moment there's no way to sync keybindings,but the main keybinding is `⌘ + ↓` to quick-access the terminal

1. Install Warp (Instructions from their [site](https://www.warp.dev/))

```bash
brew install --cask warp
```

#### ASDF
asdf Is a tool [version manager](https://asdf-vm.com/guide/introduction.html) that allows to have a **unique** version of a tool shared across teams, but also, **per project**, which allows to easily come back to old codebases.

```
brew install asdf
brew install gpg gawk
```
##### Node.JS
To Install node JS I use the previous mentioned ASDF tool version manager, installing NodeJS is as simple as adding a [plugin to asdf.](https://github.com/asdf-vm/asdf-nodejs)

```
asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
asdf install nodejs latest
asdf global nodejs latest
```


#### Github CLI
Create repositories and manipulate your git account from the terminal

```
brew install gh
```
##### Misc CLIs
1. [Railway](https://docs.railway.app/develop/cli)
2. [Netlify](https://docs.netlify.com/cli/get-started/)!
3. [Vercel](https://vercel.com/docs/cli)

#### Oh-My-ZSH
MacOS *should* come with ZSH [[Shell\|Shell]] by default (instead of bash) I use Oh-My-ZSH framework to manage plugins and aliases. Follow the guide in their [site](https://github.com/ohmyzsh/ohmyzsh/wiki).

The main plugins I use are:
- Git
- Vim
- Syntaxhighlight
#### Command-line apps
- Autojump Jump
- Fuck
- FZF
-  [[Zettelkasten/Ranger (CLI)\|Ranger (CLI)]] 
- [[Zettelkasten/Tmux\|Tmux]]

---
### Code editors

> [!NOTE] Keybindings
> Because I move across different IDEs and Text editors I try to keep in sync all my configurations 


#### Nvim
I use NeoVim for editing small files or projects, so what I look for 
```
brew install neovim

ln -s ~/dotfiles/nvim/ ~/.config/nvim
```

#### Jetbrains
I really enjoy all the Jetbrains suite as is the main site that I spend when developing web, multiplatform and Android, and I find quite easy to move, configure and share all my configurations.
For this setup we'll install the toolbox, which  allows you to install any Jetbrains IDE and (in theory) share all the configurations between them.

```
brew install --cask jetbrains-toolbox
```

#### XCode
When developing [[Zettelkasten/React Native\|React Native]] applications it seems that you need to have the XCode from the AppStore, otherwise I'd use [xcodes](https://github.com/XcodesOrg/xcodes)

```
brew install xcodesorg/made/xcodes
```

---
## References

## Relates to
- [[Zettelkasten/My Keybindings\|My Keybindings]]
