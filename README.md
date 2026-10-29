# linux-bangla

Bangla (Bengali) phonetic input setup for Arch Linux and Debian-based systems using fcitx5 and Bornopata (Avro-style).

## What this does

Sets up Bengali typing on Linux so you can type বাংলা phonetically (e.g. `ami` → আমি) with:

- **fcitx5** — input method framework
- **fcitx5-m17n + m17n-db** — multilingual input tables
- **bornopata** (AUR) — Avro-style phonetic Bengali for fcitx5
- **Ctrl + Space** — toggle between English and Bangla with a desktop notification

## Contents

- `index.html` — GitHub Pages site with setup guides for Arch, Debian, and Hyprland (includes a copy-pasteable "mega one-liner" for each)

## Quick start (Arch + Hyprland)

```bash
sudo pacman -S --needed fcitx5 fcitx5-configtool fcitx5-m17n m17n-db && yay -S --needed bornopata && bornopata-setup
```

Then add to your Hyprland config:

```lua
hl.env("GTK_IM_MODULE", "fcitx")
hl.env("QT_IM_MODULE", "fcitx")
hl.env("XMODIFIERS", "@im=fcitx")
hl.exec_cmd("fcitx5 -d")
```

And bind `CTRL + SPACE` to `~/.local/bin/im-switch` (included in the one-liner on the site).

See `index.html` for full distro-specific steps.
