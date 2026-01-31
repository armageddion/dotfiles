# dotfiles

Personal Linux dotfiles configuration featuring Hyprland Wayland window manager, Fish shell, and Kitty terminal with custom scripts and utilities.

## Overview

This repository contains a complete desktop environment setup with:

- **Hyprland** - Wayland window manager with custom keybindings, animations, and utility scripts
- **Fish Shell** - Interactive shell with custom functions, aliases, and auto-start configuration
- **Kitty Terminal** - Fast terminal emulator with custom kittens (plugins) for search and scroll marking
- **Utility Scripts** - Shell scripts for system automation, recording, window management, and AI integration

## Key Components

### Hyprland Configuration
- **Modular setup**: Main config sources separate files for environment, keybindings, rules, and general settings
- **Custom overrides**: User customizations in `hypr/custom/` directory override default configs
- **Utility scripts**: Located in `hypr/hyprland/scripts/` for zoom control, workspace management, recording, and more
- **Animations**: Custom bezier curves and transition effects for smooth window management
- **Keybindings**: Comprehensive keybinding system with submaps for different modes

### Fish Shell
- **Custom prompt**: Simple user@host directory prompt with color coding
- **Aliases**: Convenient shortcuts for common commands (`ls` → `eza --icons`, `ssh` with kitty integration)
- **Auto-start**: Automatic Hyprland launch on tty1
- **Integration**: Starship prompt support and QuickShell terminal sequences

### Kitty Terminal
- **Search kitten**: Full-text search with regex support and keyboard navigation
- **Scroll mark kitten**: Navigate through marked positions in terminal history
- **Custom keybindings**: Integrated search (Ctrl+F) and font size controls
- **Shell integration**: Uses Fish shell by default with kitty-specific SSH handling

## Utility Scripts

### Window Management
- `zoom.sh` - Control Hyprland cursor zoom (1.0-3.0 range)
- `workspace_action.sh` - Perform workspace operations with arithmetic
- `launch_first_available.sh` - Launch first available application from a list

### System Tools
- `record.sh` - Screen recording with wf-recorder, supporting region/fullscreen with optional audio
- `fuzzel-emoji.sh` - Emoji picker with type/copy/both modes (emoji data embedded in script)
- `status.sh` - Battery status display for Hyprlock

### AI Integration
- `show-loaded-ollama-models.sh` - Display currently running Ollama models with JSON output option
- `primary-buffer-query.sh` - Query primary buffer content

## File Structure

```
hypr/
├── hyprland/              # Main Hyprland configuration
│   ├── *.conf             # Config sections (general, keybinds, rules, etc.)
│   └── scripts/           # Utility scripts
├── custom/                # User overrides (takes precedence)
├── hyprlock.conf          # Lock screen configuration
└── shaders/               # Custom GLSL shaders (solarized, invert, etc.)
fish/
├── config.fish            # Main shell configuration
└── auto-Hypr.fish         # Auto-start Hyprland on tty1
kitty/
├── kitty.conf             # Terminal configuration
├── search.py              # Search kitten plugin
└── scroll_mark.py         # Scroll marking kitten plugin
```

## Dependencies

Required tools for full functionality:
- `hyprland` - Wayland window manager
- `fish` - Interactive shell
- `kitty` - Terminal emulator
- `fuzzel` - Application launcher (for emoji picker)
- `wf-recorder` - Screen recording
- `slurp` - Region selection
- `jq` - JSON processing
- `notify-send` - Desktop notifications
- `starship` - Custom shell prompt (optional)
- `ollama` - AI model integration (optional)

## Usage

1. Clone this repository to `~/.config/`
2. Ensure all dependencies are installed
3. The configuration will be automatically sourced by the respective applications
4. Some scripts may need executable permissions: `chmod +x hypr/hyprland/scripts/*.sh`

## Customization

- Add personal overrides in `hypr/custom/` - these take precedence over default configs
- Modify Fish aliases and functions in `fish/config.fish`
- Add custom Kitty kittens or modify keybindings in `kitty/kitty.conf`
- Extend utility scripts or add new ones to `hypr/hyprland/scripts/` 
