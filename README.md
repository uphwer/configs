# 🌿 dotfiles & configs

A clean, cohesive Wayland rice featuring [Niri](https://github.com/YaLTeR/niri) (scrollable tiling compositor) and the earthy **Everforest Dark Medium / Noctalia** aesthetic.

![Wayland](https://img.shields.io/badge/Wayland-Niri-598381?style=flat-square&logo=wayland&logoColor=white)
![Terminal](https://img.shields.io/badge/Terminal-Kitty-green?style=flat-square&logo=kitty&logoColor=white)
![Theme](https://img.shields.io/badge/Theme-Everforest%20%2F%20Noctalia-a7c080?style=flat-square)
![Launcher](https://img.shields.io/badge/Launcher-Fuzzel-dbbc7f?style=flat-square)

---

## 🖥️ System & Tools

| Component | Software | Description |
| :--- | :--- | :--- |
| **Compositor / WM** | [Niri](https://github.com/YaLTeR/niri) | Scrollable-tiling Wayland compositor with smooth column workflows |
| **Shell & Widgets** | [Quickshell](https://quickshell.outfoxxed.me/) | Custom `noctalia-shell` desktop interface |
| **Terminal** | [Kitty](https://sw.kovidgoyal.net/kitty/) | GPU-accelerated terminal emulator |
| **Application Launcher** | [Fuzzel](https://codeberg.org/dnkl/fuzzel) | Fast, lightweight Wayland dmenu/rofi alternative |
| **File Manager** | [Yazi](https://github.com/sxyazi/yazi) | Blazing-fast terminal file manager |
| **System Fetch** | [Fastfetch](https://github.com/fastfetch-cli/fastfetch) | Detailed system overview with custom color-mapped ASCII art |
| **Display Font** | `Bitstream Vera Sans Mono` | Clean monospace typography for terminal and launcher |

---

## 🎨 Palette (Everforest / Noctalia)

Harmonious nature-inspired dark palette:

| Role | Color | Hex |
| :--- | :--- | :--- |
| **Background (bg0)** | ![#2d353b](https://via.placeholder.com/14/2d353b/2d353b.png) | `#2d353b` |
| **Foreground (fg)** | ![#d3c6aa](https://via.placeholder.com/14/d3c6aa/d3c6aa.png) | `#d3c6aa` |
| **Active Accent (Green)** | ![#a7c080](https://via.placeholder.com/14/a7c080/a7c080.png) | `#a7c080` |
| **Urgent / Error (Red)** | ![#e67e80](https://via.placeholder.com/14/e67e80/e67e80.png) | `#e67e80` |
| **Warning / Special (Orange)** | ![#e69875](https://via.placeholder.com/14/e69875/e69875.png) | `#e69875` |
| **Highlight (Aqua)** | ![#7fbbb3](https://via.placeholder.com/14/7fbbb3/7fbbb3.png) | `#7fbbb3` |

---

## 📂 Repository Structure

```text
.
├── fastfetch/
│   ├── config.jsonc         # Custom Fastfetch layout (Environment, Software, Hardware)
│   └── ascii-art.txt        # Full-color ANSI custom logo
├── fuzzel/
│   └── fuzzel.ini           # Fuzzel launcher styled with Everforest & custom prompt
├── kitty/
│   ├── kitty.conf           # Main Kitty configuration with font & theme includes
│   ├── current-theme.conf   # Active Noctalia color palette
│   ├── everforest.conf      # Base Everforest palette definition
│   └── themes/noctalia.conf # Noctalia theme definition
├── niri/
│   ├── config.kdl           # Niri display, input, animations, keybindings & autostart
│   └── noctalia.kdl         # Niri layout theme (focus rings, borders, tab indicators)
└── yazi/
    └── theme.toml           # Directory highlighting & custom colors
```

---

## ⌨️ Essential Keybindings (Niri)

| Shortcut | Action |
| :--- | :--- |
| `Mod` + `T` | Spawn terminal (`kitty`) |
| `Mod` + `D` | Run application launcher (`fuzzel`) |
| `Mod` + `W` | Toggle column tabbed display |
| `Mod` + `V` | Toggle floating mode for active window |
| `Mod` + `Shift` + `V` | Switch focus between floating and tiling layers |
| `Mod` + `-` / `Mod` + `=` | Decrease / Increase column width by 10% |
| `Mod` + `Shift` + `S` | Interactive screenshot tool |
| `Ctrl` + `Print` | Capture entire screen |
| `Alt` + `Print` | Capture focused window |
| `Mod` + `Shift` + `P` | Power off monitors |
| `Mod` + `Shift` + `E` | Quit session (with confirmation) |

---

## 🚀 Installation

These configurations are designed to reside in `~/.config/`:

### Option A: Using [GNU Stow](https://www.gnu.org/software/stow/) (Recommended)

```bash
git clone https://github.com/uphwer/configs.git ~/dotfiles
cd ~/dotfiles
stow --target="$HOME/.config" fastfetch fuzzel kitty niri yazi
```

### Option B: Manual Symlinks

```bash
git clone https://github.com/uphwer/configs.git ~/configs
mkdir -p ~/.config

for folder in fastfetch fuzzel kitty niri yazi; do
  ln -sfn "$HOME/configs/$folder" "$HOME/.config/$folder"
done
```

> **Note**: Verify your monitor resolution and scale in `niri/config.kdl` under the `output "eDP-1"` block if using a different display output.
