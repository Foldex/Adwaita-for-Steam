# Adwaita for Steam

A skin to make Steam look more like a native GNOME app

<p align="center"><img src="screenshot.png?raw=true"/></p>

## Current state and plans

* **Main window**: done.
* **Settings**: mostly done.
* **New library, new chat, other web-based client parts**: mostly done, with slight [limitations](#limitations).
* **New Big Picture**: Not done.
* **Overlay**: done.
* **Small mode**: done.
* **Old library, old chat, other old unused windows**: not planned.
* **Recoloring**: colors can be changed via making a new theme. See [colorthemes](colorthemes) dir.
* **Light theme**: not planned, would require redrawing all assets to be visible on light backgrounds.

### Limitations

* **Rounded corners**: impossible to do in a Steam skin, use [Rounded Window Corners extension](https://github.com/yilozt/rounded-window-corners) or [mutter-rounded](https://github.com/yilozt/mutter-rounded) on GNOME
* **Height of menu/sidebar items**: doesn't seem to be possible to increase
* **Library Theming**: While the installer will patch steam files to allow theming the library, these files may be reset by steam updates. A reinstall is currently needed to repatch them.

## Requirements

* [Cantarell fonts](https://gitlab.gnome.org/GNOME/cantarell-fonts) as static fonts. Some distros install Cantarell as a variable font that is not supported by Steam, see [#45](https://github.com/tkashkin/Adwaita-for-Steam/issues/45). An option to install these is included in the install script.
* The skin was created for the Linux version of Steam and wasn't tested on Windows or macOS. It will work with some visual problems.

## Previews

<details><summary>Previews</summary>

<details><summary>Adwaita</summary>

![Adwaita](/colorthemes/adwaita/preview.png?raw=true)

</details>

<details><summary>Breeze</summary>

![Breeze](/colorthemes/breeze/preview.png?raw=true)

</details>

<details><summary>Catppuccin-Frappe</summary>

![Catppuccin-Frappe](/colorthemes/catppuccin-frappe/preview.png?raw=true)

</details>

<details><summary>Catppuccin-Macchiato</summary>

![Catppuccin-Macchiato](/colorthemes/catppuccin-macchiato/preview.png?raw=true)

</details>

<details><summary>Catppuccin-Mocha</summary>

![Catppuccin-Mocha](/colorthemes/catppuccin-mocha/preview.png?raw=true)

</details>

<details><summary>Dracula</summary>

![Dracula](/colorthemes/dracula/preview.png?raw=true)

</details>

<details><summary>Gruvbox</summary>

![Gruvbox](/colorthemes/gruvbox/preview.png?raw=true)

</details>

<details><summary>Kate</summary>

![Kate](/colorthemes/kate/preview.png?raw=true)

</details>

<details><summary>Nord</summary>

![Nord](/colorthemes/nord/preview.png?raw=true)

</details>

<details><summary>One Pro</summary>

![One Pro](/colorthemes/one-pro/preview.png?raw=true)

</details>

<details><summary>Pop</summary>

![Pop](/colorthemes/pop/preview.png?raw=true)

</details>

<details><summary>Tokyo Night</summary>

![Tokyo Night](/colorthemes/tokyo-night/preview.png?raw=true)

</details>

<details><summary>Tomorrow Night</summary>

![Tomorrow Night](/colorthemes/tomorrow-night/preview.png?raw=true)

</details>

<details><summary>Yaru</summary>

![Yaru](/colorthemes/yaru/preview.png?raw=true)

</details>

</details>

## Installation

### With installer script

```bash
git clone https://github.com/tkashkin/Adwaita-for-Steam
cd Adwaita-for-Steam
./install.py
```

#### Arguments

| Argument         | Short  | Required Values                  | Description                                              |
| ---------------- | ------ | -------------------------------- | -------------------------------------------------------- |
| --color-theme    | -c     | [Colortheme](colorthemes)        | Change color theme                                       |
| --font-install   | -fi    |                                  | Installs static Cantarell fonts                          |
| --list-options   | -l     |                                  | List available patches, themes, and web extras           |
| --no-steam-patch | -nsp   |                                  | Do not patch steam client files                          |
| --target         | -t     | normal / flatpak / [custom dir]  | Choose target location for install (default: both)       |
| --web-theme      | -w     | full / base / none               | Choose web theme variant (default: full)                 |
| --web-extras     | -we    | [Web Extra](web/extras)          | Enable one or multiple web theme extras                  |

#### Example Usage

```bash
# List options
./install.py -l
# Install with options
./install.py -c nord -fi -p windowcontrols/right-all -we login/hide_qr -we library/hide_whats_new
```

### With graphical installer

Use the [graphical installer](https://github.com/Foldex/AdwSteamGtk) by [@Foldex](https://github.com/Foldex).

<a href="https://flathub.org/apps/details/io.github.Foldex.AdwSteamGtk"><img width="200" alt="Download on Flathub" src="https://flathub.org/assets/badges/flathub-badge-i-en.svg"/></a>

### Manual installation

Note: Installation with this method is lacking in several features, one of the installers is preferred.

1. Download the [latest skin version](https://github.com/tkashkin/Adwaita-for-Steam/archive/master.zip)
2. Extract `Adwaita` directory into Steam `skins` directory (create if it doesn't exist):
   * **Linux**: `~/.steam/steam/skins` or `~/.local/share/Steam/skins`
   * **Linux (flatpak)**: `~/.var/app/com.valvesoftware.Steam/.local/share/Steam/skins`
   * ~~Windows~~ (untested): `C:\Program Files (x86)\Steam\skins` by default
   * ~~macOS~~ (untested): `~/Library/Application Support/Steam/Steam.AppBundle/Steam/Contents/MacOS/skins`
3. Open Steam and select `Adwaita` skin in Settings > Interface (restart Steam if it doesn't appear in the list)

## Uninstallation

Since the installer patches steam client files directly, simply changing the steam skin will not undo all changes.

Reinstall with `--web-theme none` to unpatch these files.
