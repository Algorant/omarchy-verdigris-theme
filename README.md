# Verdigris for Omarchy

This is the Verdigris **Omarchy theme port**. The canonical identity and extended palette live in [`../css/palette.json`](../css/palette.json) (version 0.1.2); `colors.toml` maps them into Omarchy's semantic/ANSI slots. The wallpaper is a simple, generated 2560×1440 PNG using Verdigris colors. No bundled Omarchy files need to be edited.

## Install or update locally

Do **not** run `omarchy theme install` on the root of this repository: it contains many application ports, not an Omarchy theme at its top level. Copy only this directory's theme files into your user theme directory:

```sh
mkdir -p ~/.config/omarchy/themes/verdigris/backgrounds
cp ~/Projects/verdigris/omarchy/colors.toml ~/.config/omarchy/themes/verdigris/
cp ~/Projects/verdigris/omarchy/backgrounds/verdigris.png ~/.config/omarchy/themes/verdigris/backgrounds/
omarchy dev theme preview ~/.config/omarchy/themes/verdigris/colors.toml
omarchy theme set verdigris
```

### OLED variant

[`oled/colors.toml`](./oled/colors.toml) is the same theme with the warmer cream foreground `#f2d6a2`, for OLED panels where vellum reads too cool (x1nano). Install it as a second theme and pick it per machine:

```sh
mkdir -p ~/.config/omarchy/themes/verdigris-oled/backgrounds
cp ~/Projects/verdigris/omarchy/oled/colors.toml ~/.config/omarchy/themes/verdigris-oled/
cp ~/Projects/verdigris/omarchy/backgrounds/verdigris.png ~/.config/omarchy/themes/verdigris-oled/backgrounds/
omarchy theme set verdigris-oled
```

If your checkout is elsewhere, replace `~/Projects/verdigris` accordingly. Re-copy modified files and re-run `omarchy theme set verdigris` after palette or background changes. `omarchy theme set gruvbox` restores the previous stock theme. The active wallpaper can be cycled or replaced independently via `omarchy theme bg`.

## Palette mapping

| Omarchy role | Verdigris source / choice | Reason |
| --- | --- | --- |
| Background | `#1d2021` | Dark reading surface shared with Ghostty, Pi, and btop ports; ashbronze is too bright for a full-screen dark UI. |
| Foreground | vellum `#ebdbb2` (OLED variant: warm cream `#f2d6a2`) | Canonical text color, matching the other ports. On OLED panels vellum read too cool, so `oled/` keeps the warmer cream. |
| Accent | fern `#8ec07c` | Bright primary highlight, matching the Pi port. |
| Selection / brown | ashbronze `#665c54` | Weathered-metal accent and selection background. |
| Green / bright green | patina `#689d6a` / fern `#8ec07c` | Quiet versus bright green. |
| Blue / bright blue | teal `#458588` / aqua `#83a598` | Secondary versus brighter cool accent. |
| Yellow / orange | ochre `#e6bf86` / deep-copper `#b9805f` | Brass and copper roles. |
| Magenta | ink-violet `#8989b0` | Rare special/ANSI accent. |
| Red | `#fb4934` | The existing Ghostty port's readable red; canonical oxblood `#74363d` is too dark for error text on the base background. |

Muted text `#928374`, soft light text `#d4be9a`, and derived dark surfaces follow existing Verdigris app ports. The foreground is canonical vellum `#ebdbb2`, like the other ports. The warmer `#f2d6a2` trial lives on as the OLED variant. No canonical colors in `css/palette.json` are changed here. Omarchy generates application settings (including Ghostty, shell, btop, Pi, Obsidian and a Neovim fallback) from this theme. App-specific Verdigris ports and the standalone [`verdigris.nvim`](https://github.com/Algorant/verdigris.nvim) remain independent; review their integration before forcing Omarchy's generated styling over a separately configured app. In particular, Ghostty's Omarchy `config-file` loads the generated palette, whereas the dotfiles' Ghostty theme may explicitly set another palette. Pick one owner when deploying dotfiles.

## Wallpaper

`backgrounds/verdigris.png` is a deliberately quiet dark gradient and low-contrast patina/ashbronze/aqua circles, generated for this port with ImageMagick. It is a starting point, not a canonical Verdigris color specification. Replace or supplement it with other PNG/JPEG/WebP wallpapers (mind image rights) as desired.
