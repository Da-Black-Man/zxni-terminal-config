# My Terminal Setup

A complete Mac terminal environment based on the Catppuccin Mocha color theme.

---

## Terminal: Ghostty

**Config location:** `~/.config/ghostty/config`

| Setting | Value |
|---|---|
| Theme | Catppuccin Mocha |
| Font | JetBrainsMono Nerd Font Mono |
| Font Size | 19 |
| Background Opacity | 0.7 |
| Background Blur | 20 |
| Option as Alt | true (needed for terminal shortcuts) |

**Install:**
```
brew install --cask ghostty
```

---

## Terminal (Alternative): WezTerm

**Config location:** `~/.config/wezterm/wezterm.lua`

| Setting | Value |
|---|---|
| Theme | Catppuccin Mocha |
| Font | JetBrains Mono |
| Font Size | 16 |
| Background Blur | 30 |
| Tab Bar | Disabled |

**Install:**
```
brew install --cask wezterm
```

---

## Prompt: Starship

**Config location:** `~/.config/starship/starship.toml`

- Left prompt: directory + character
- Right prompt: git branch, git status, command duration
- Color palette: Catppuccin Mocha
- Git icons on the right side

**Install:**
```
brew install starship
```

---

## Shell: Nushell

**Config locations:**
- `~/.config/nushell/config.nu` — main config, aliases, SDM functions
- `~/.config/nushell/env.nu` — environment variables, PATH

**Key setup:**
- Starship prompt wired up via `PROMPT_COMMAND`
- PATH includes `/opt/homebrew/bin`, `/opt/homebrew/sbin`, user-local bins, and mise shims
- Editor set to `nvim`

**SDM shortcuts:**
| Command | Description |
|---|---|
| `sdm-start` | Start SDM listener + connect all resources |
| `sdm-stop` | Disconnect all resources + stop listener |
| `sdm-find` | Search SDM resources with filters (see below) |
| `sdm-explore` | Browse all SDM resources interactively |

**sdm-find flags:**
```
sdm-find [pattern]
  --environment  filter by env (prod, stg, dev, test)
  --tenant       filter by tenant (fedex, paradox, mchire)
  --service      filter by service (job, featureflag)
  --type         filter by type (mysql, redis, httpNoAuth)
  --connected    show only connected resources
```

**Install:**
```
brew install nushell
```

---

## Multiplexer: tmux

**Config location:** `~/.config/tmux/tmux.conf`

| Setting | Value |
|---|---|
| Theme | Catppuccin (omerxx fork) |
| Prefix | Ctrl+A |
| Status position | Top |
| Mouse | Enabled |
| Base index | 1 |

**Plugins (via TPM):**
- `tmux-plugins/tpm` — plugin manager
- `tmux-plugins/tmux-sensible` — sensible defaults
- `tmux-plugins/tmux-yank` — clipboard yank
- `tmux-plugins/tmux-resurrect` — save/restore sessions
- `tmux-plugins/tmux-continuum` — auto-save sessions
- `fcsonline/tmux-thumbs` — quick copy with hints
- `sainnhe/tmux-fzf` — fuzzy finder integration
- `wfxr/tmux-fzf-url` — open URLs with fzf
- `omerxx/catppuccin-tmux` — Catppuccin theme
- `omerxx/tmux-sessionx` — session manager (bound to `o`)
- `omerxx/tmux-floax` — floating pane (bound to `p`)

**Key bindings:**
| Shortcut | Action |
|---|---|
| `Ctrl+A` | Prefix |
| `prefix + o` | Session switcher (sessionx) |
| `prefix + p` | Floating pane (floax) |
| `prefix + I` | Install TPM plugins |

**Install:**
```
brew install tmux
# Clone TPM:
git clone https://github.com/tmux-plugins/tpm ~/.config/tmux/plugins/tpm
# Then inside tmux: prefix + I
```

---

## Font: JetBrainsMono Nerd Font

Required for terminal icons (git symbols, folder icons, arrows).

**Install:**
```
brew install --cask font-jetbrains-mono-nerd-font
```

---

## Shell: Zsh

**Config location:** `~/.zshrc`

**Includes:**
- NVM (Node Version Manager)
- Starship prompt init
- Zoxide (smart cd)
- Atuin (shell history)
- Direnv
- Git aliases: `gc`, `gca`, `gp`, `gpu`, `gst`, `glog`, etc.
- Docker aliases: `dco`, `dps`, `dpa`, `dl`, `dx`
- Kubernetes aliases: `k`, `ka`, `kg`, `kd`, `kdel`, `kl`, etc.
- Eza aliases: `l`, `lt`, `ltree`

---

## Color Theme: Catppuccin Mocha

Used consistently across Ghostty, WezTerm, tmux, and Starship.

Key colors:
| Name | Hex |
|---|---|
| Base | `#1e1e2e` |
| Text | `#cdd6f4` |
| Green | `#a6e3a1` |
| Blue | `#89b4fa` |
| Mauve | `#cba6f7` |
| Red | `#f38ba8` |
| Yellow | `#f9e2af` |
| Peach | `#fab387` |

---

## File Structure

```
zxni-terminal-config/
├── README.md
├── ghostty/
│   └── config
├── wezterm/
│   └── wezterm.lua
├── starship/
│   └── starship.toml
├── nushell/
│   ├── config.nu
│   └── env.nu
├── tmux/
│   ├── tmux.conf
│   └── tmux.reset.conf
└── zsh/
    └── .zshrc
```

## Install Locations

Copy each file to its destination:
```
ghostty/config        → ~/.config/ghostty/config
wezterm/wezterm.lua   → ~/.config/wezterm/wezterm.lua
starship/starship.toml → ~/.config/starship/starship.toml
nushell/config.nu     → ~/.config/nushell/config.nu
nushell/env.nu        → ~/.config/nushell/env.nu
tmux/tmux.conf        → ~/.config/tmux/tmux.conf
tmux/tmux.reset.conf  → ~/.config/tmux/tmux.reset.conf
zsh/.zshrc            → ~/.zshrc
```
