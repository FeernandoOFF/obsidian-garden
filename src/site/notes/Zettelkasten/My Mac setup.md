---
{"dg-publish":true,"permalink":"/zettelkasten/my-mac-setup/","title":"My development setup","tags":["status/todo","core/tech","outputs/ideas"],"noteIcon":"","created":"2023-01-23T11:06:40.000+00:00","updated":"2023-11-15T18:10:44.128+00:00"}
---


# Mac Setup

The procedure I follow when cleaning or setting up a new Mac

## General setup
### System Settings

### Finder Settings

1. Dock to auto hide
2. Show hidden files
3. Don't show recent aplcations
4. Configurate Trackpad
### Arc
Arc is the **best browser** that I've ever tried, you can download it on their [website](https://arc.net/).

### 1Password
1Password is my [[Password manager\|Password manager]] and it is available in all platforms and even CLI! You can download it in their [website](https://1password.com/downloads/command-line/)

### SKHD
### Karabiner
### Yabai

## Development Setup

#### ### Homebrew Setup
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
1. Railway
2. Netlify
3. Vercel

##### ZSH
##### Ranger
[[Zettelkasten/Ranger (CLI)\|Ranger (CLI)]]
##### Tmux
[[Zettelkasten/Tmux\|Tmux]]
##### Jump
#### Dotenv

### Code editors

#### Nvim
```
brew install neovim
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

## Keybindings
### Mac Keybinding
> The main key that I use for system-movement are 
>⌥  and ⇪ - which is a special character mapped in Karabiner


| Action                        | Keybinding              |
|:----------------------------- | ----------------------- |
| Raycast                       | `⌘ -  Space`          |
| Floating-Notes                | `⇪ - .`         |
| Raycast AI                    | `⇪ - /`                        |
| Translate                     | `⇪ - ,`         |
| **WINDOW MANAGEMENT**         |                         |
| *Focus*                       |                         |
| Focus L-R-T-B                 | `OPT - [h/j/k/l]`       |
| Focus Monitor (North, south)  | `⇪ - [w/s]`           |
| Maximise                      | `⇪ - m`               |
| Toggle Window Float           | `⇪- t`                |
| *Move Windows*                |                         |
| Move to Desktop               | `⇪ - [1,2,3]` |
| Move to previous/next dekstop | `OPT - Shift - [P/N]`   |
| Move to Monitor               | `⎇ - ⇪ - [w/s]`   |
| Rotate Layout                 | `⎇ - ⇪ - R`       |
| Flip X/Y axis                 | `⎇ - ⇪ - [x/y]`   |
| **1Password**                 |                         |
| 1Password Quick Access        | `⇪ - Space`   |

### Editors Keybindings
> Main Movement keys are 
> ⌘ - Command 
> ⇧ - Shift
> ⎇ - Alt
> ⌤ - CTRL

| Action                        | Keybinding            | JetBrainsIDEs | XCode | Obsidian | VSCode | Vim |
| ----------------------------- | --------------------- | ------------- | ----- | -------- | ------ | --- |
| **APP MENU**                  |                       |               |       |          |        |     |
| Toggle right panel            | `⌘ + ⇧ + R`           | ✅            | ✅    | ✅       |        |     |
| Toggle Left Panel  (TO-Check) | `⌘ + ⇧ + L`           | ✅            | ✅    | ✅       |        |     |
| Toggle  Bottom Panel          | `⌘ + ⇧ + B`           |               |       |          |        |     |
| Toggle  Terminal              | `⌘ + ~`               | ✅            | ⏹️    | ⏹️       |        |     |
| Search File                   | `⌘ + P`               | ✅            | ✅    | ✅       |        |     |
| Open  Command/Editor search   | `⌘ +  ⇧ + P`          | ✅            |       | ✅       |        |     |
| Find in file                  | `⌘ + f`               | ✅            | ✅    | ✅       |        |     |
| Find in codebase              | `⌘ - ⇧ + F `          | ✅            | ✅    | ✅       |        |     |
| Run App                       | `⌘ - R `              | ✅            |       | ⏹️       |        |     |
| **FILE MENU**                 |                       |               |       |          |        |     |
| Create new File               | `⌘ + n`               | ✅            |       | ✅       |        |     |
| Close file                    | `⌘ + w`               | ✅            |       | ✅       |        |     |
| Next tab                      | `⌘ - ⇧ + }`           | ✅            | ✅    | ✅       |        |     |
| Previous file                 | `⌘ - ⇧ + {`           | ✅            | ✅    | ✅       |        |     |
| Switch recently used          | `CTRL + Tab `         | ✅            |       | ✅       |        |     |
| **Editting**                  |                       |               |       |          |        |     |
| Toggle Fold Block             | `⌘ - .`               | ✅            |       | ✅       |        |     |
| Fold All                      | `⌘ - ⇧ + .`           | ✅            |       | ✅       |        |     |
| Unfold All                    | `⌘ - ⇧ + ,`           | ✅            |       | ✅       |        |     |
| Rename variable / File        | `F2`                  | ✅            |       |          |        |     |
| Move Line                     | `⎇ + up/down`         | ✅            |       |          |        |     |
| **Split Panels**              |                       |               |       |          |        |     |
| Split to right                | `ctrl + w`            |               |       |          |        |     |
| Focus to right                | `ctrl + l`            |               |       |          |        |     |
| Focus to left                  | `ctrl + h`                      |               |       |          |        |     |
| Close split                   | `⌘ + ⇧ + w`              |               |       |          |        |     |
| **Multiple cursors**          |                       |               |       |          |        |     |
| Next Selected                 |                       |               |       |          |        |     |
| Insert cursor below/above     | `ctrl + ⎇  + up/down` |               |       |          |        |     |


## References
