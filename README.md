# 🎯 Astur Tactical Rice (Hyprland-Inspired for Windows 11)

A minimal, high-performance, Hyprland-inspired tiling window manager rice for **Astur 2.4.0** on Windows 11, color-matched to dark metallic wallpaper with tactical sage green accents.

Designed specifically for competitive gaming (Counter-Strike 2 @ 240Hz), low latency, and zero window management overhead.

---

## 🎨 Color Palette & Aesthetic

| Element | Hex Color | Description |
|---|---|---|
| **Base Background** | `#121316` | Deep charcoal / dark gunmetal matte |
| **Surface / Card** | `#1C1E23` | Elevated surface for status bar pills & popups |
| **Active Accent** | `#9EAC6C` | Tactical Sage Green (sampled directly from wallpaper midtones) |
| **Foreground Text**| `#E2E5EB` | High-contrast matte white / light slate |
| **Muted / Inactive**| `#585E6A` | Gunmetal slate for empty marks & secondary stats |
| **Border (Focused)**| `#9EAC6C` | 1px clean tactical sage accent border |
| **Border (Unfocused)**| `#262A30` | 1px subtle gunmetal border |

---

## ⚡ Performance & Competitive Gaming Highlights

- **`unfocused_opacity = 1.0`**: Avoids adding `WS_EX_LAYERED` to windows, preventing DWM composition path overhead and input latency.
- **`acrylic = false`**: Disables undocumented experimental acrylic blur to guarantee rock-solid frame times and 0% GPU draw while gaming.
- **Snappy Animations (`120ms` spring)**: Tuned specifically for high-refresh-rate displays (up to 240Hz) with Hyprland-style spring overshoot-and-settle.
- **Window Rules**: Explicitly excludes `cs2.exe`, `Overwatch.exe`, `Valorant.exe`, and Steam Web Helper from tiling hooks:
  ```ini
  window_rules = ignore|cs2.exe ;; ignore|steamwebhelper.exe ;; ignore|Overwatch.exe ;; ignore|Valorant.exe
  ```

---

## 🚀 Key Features

1. **Floating Status Bar (`navbar.conf`)**:
   - Floating pill / island layout (`shape = floating`, `radius = 8`, `margin = 8`).
   - Native Windows Segoe Fluent Icons (`icon_mode = glyph`).
   - Active workspace pill in tactical sage green (`#9EAC6C`).
   - Lightweight live system monitoring (CPU, RAM, Volume, Date, Clock).
2. **App Launcher & System Menu (`astur.conf`)**:
   - `Alt + Space`: Fast MRU-ranked app & file search styled in matching dark palette.
   - `Alt + Shift + Space`: System power & setup menu.
3. **Hotkeys**:
   - `Alt + Enter`: Terminal (`wt.exe`).
   - `Alt + 1-9, 0`: Switch workspaces.
   - `Alt + Shift + 1-9, 0`: Move window to workspace.
   - `Alt + Left-Drag`: Move window anywhere on screen.
   - `Alt + Right-Drag`: Resize window from nearest corner.
   - `Alt + T`: Toggle tiling on/off.
   - `Alt + W`: Close focused window.

---

## 📂 File Structure

- `astur.conf`: Main window manager configuration (gaps, borders, animations, rules).
- `navbar.conf`: Status bar configuration (shapes, widgets, colors, typography).

---

## 🔄 How to Restore Defaults

A backup of the original configuration is saved at:
`%USERPROFILE%\.astur\backups\pre_theme_20261028\`

To restore:
```powershell
Copy-Item "$env:USERPROFILE\.astur\backups\pre_theme_20261028\astur.conf.orig" "$env:USERPROFILE\.astur\astur.conf" -Force
Copy-Item "$env:USERPROFILE\.astur\backups\pre_theme_20261028\navbar.conf.orig" "$env:USERPROFILE\.astur\navbar.conf" -Force
```
Astur hot-reloads the changes in ~0.1 seconds.
