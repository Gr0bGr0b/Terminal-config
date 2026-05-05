# Terminal Config

Personal configuration files for Tmux, Zsh, and Neovim to create a consistent terminal development environment that works across different machines.

## Overview

This repository contains curated configuration files for:
- **Tmux** - Terminal multiplexer for window and pane management
- **Zsh** - Z shell with Oh My Zsh framework and plugins
- **Neovim** - Modern terminal-based text editor

## Directory Structure

```
Terminal-config/
├── Tmux/
│   └── .tmux.conf          # Tmux configuration
├── Zsh/
│   └── .zshrc              # Zsh configuration
├── Neovim/                 # Neovim configuration
└── README.md
```

## Tmux Configuration

### Features

- **Indexed from 1**: Windows and panes start at 1 instead of 0 for easier navigation
- **Mouse Support**: Full mouse support enabled for intuitive pane selection and resizing
- **Alt+Arrow Navigation**: Quick pane navigation using Alt + arrow keys
- **Config Reload**: Press `Prefix + r` to reload the configuration
- **Extended History**: 10,000 line history limit
- **256 Color Support**: Full color terminal support

### Plugins

The configuration includes the following plugins via [TPM](https://github.com/tmux-plugins/tpm) (Tmux Plugin Manager):

- **tmux-sensible**: Sensible defaults and best practices
- **tmux-resurrect**: Persists tmux sessions across reboots
- **tmux-continuum**: Automatic session saving and restoration
- **Catppuccin**: Beautiful Mocha theme with rounded window status style

### Installation

1. Copy `.tmux.conf` to your home directory:
   ```bash
   cp Tmux/.tmux.conf ~/.tmux.conf
   ```

2. Install TPM if not already installed:
   ```bash
   git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
   ```

3. Reload tmux or start a new session:
   ```bash
   tmux source-file ~/.tmux.conf
   ```

4. Install plugins by pressing `Prefix + I` (default prefix is `Ctrl+b`)

## Zsh Configuration

### Features

- **Oh My Zsh Framework**: Powerful shell framework with community-driven plugins and themes
- **Jovial Theme**: Custom prompt with git status indicators and unicode characters
- **Smart Plugins**: Curated set of plugins for better productivity:
  - **git**: Git aliases and completions
  - **zoxide**: Smarter `cd` with frecency tracking
  - **urltools**: URL manipulation from command line
  - **bgnotify**: Desktop notifications for long-running commands
  - **zsh-autosuggestions**: Fish-like autosuggestions
  - **zsh-syntax-highlighting**: Command syntax highlighting
  - **zsh-history-enquirer**: Better history search
- **Auto-connect Tmux**: Automatically connects to tmux on shell startup
- **Package Manager Integration**: Homebrew and NVM support

### Installation

1. Install Oh My Zsh (if not already installed):
   ```bash
   sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
   ```

2. Copy `.zshrc` to your home directory:
   ```bash
   cp Zsh/.zshrc ~/.zshrc
   ```

3. Install required plugins (if not already installed):
   ```bash
   # zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

   # zsh-syntax-highlighting
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

   # zsh-history-enquirer
   git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-enquirer
   ```

4. Reload the shell:
   ```bash
   source ~/.zshrc
   ```

### Theme Customization

The Jovial theme is customized with:
- Top corner: `╭─`
- Bottom corner: `╰─`
- Git clean status: `✔`
- Git dirty status: `✘✘✘`
- Arrow: `─➤`
- Custom git-clean and git-dirty arrows with emoticons

## Neovim Configuration

Configuration files for Neovim are included in the `Neovim/` directory.

### Installation

Copy the Neovim configuration to your config directory:
```bash
cp -r Neovim/* ~/.config/nvim/
```

## Quick Setup

To quickly set up all configurations on a new machine:

```bash
# Clone the repository
git clone <repository-url> ~/Terminal-config

# Copy Zsh config
cp ~/Terminal-config/Zsh/.zshrc ~/.zshrc

# Copy Tmux config
cp ~/Terminal-config/Tmux/.tmux.conf ~/.tmux.conf

# Copy Neovim config
mkdir -p ~/.config/nvim
cp -r ~/Terminal-config/Neovim/* ~/.config/nvim/

# Install Oh My Zsh (if not already installed)
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install Zsh plugins
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-enquirer

# Install TPM for Tmux
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# Reload Zsh and Tmux
source ~/.zshrc
tmux kill-server
tmux new-session -d -s main
# Then press Prefix + I to install Tmux plugins
```

## Key Bindings

### Tmux

| Binding | Action |
|---------|--------|
| `Alt+Left` | Select left pane |
| `Alt+Right` | Select right pane |
| `Alt+Up` | Select upper pane |
| `Alt+Down` | Select lower pane |
| `Prefix+r` | Reload configuration |

*Note: Default prefix is `Ctrl+b`*

## Requirements

- Tmux 3.0 or higher
- Neovim 0.7 or higher (for Neovim configuration)
- Git (for plugin management)

## License

Personal configuration repository
