# Cita themes for Marta

Cita light and dark themes for the Marta file manager and its built-in terminal, etty.

## Files

- `CitaLight.theme` and `CitaDark.theme` are Marta themes.
- `CitaLight.ettyTheme` and `CitaDark.ettyTheme` are etty terminal themes.
- `config.txt` is my Marta config.

## Install

Copy the theme files to the Marta themes folder:

```sh
mkdir -p ~/Library/Application\ Support/org.yanex.marta/Themes
cp Cita*.theme Cita*.ettyTheme ~/Library/Application\ Support/org.yanex.marta/Themes/
```

## Config

Open the config with `Marta → Preferences`, or edit `~/Library/Application Support/org.yanex.marta/conf.marco`. Then add this:

```
environment {
  terminal "iTerm2"
  textEditor "/Applications/Visual Studio Code - Insiders.app"
}

behavior {
  theme "Cita Light"
  layout {
    alwaysShowTabBar true
  }
}

etty {
  theme "CitaLight"
  useMainThemeColors false

  environ {
    fish_features "no-query-term"
  }

  fonts {
    normal [ "Maple Mono" 13 ]
  }
}

fonts {
  actionBar [ "Maple Mono" 13 ]
  breadcrumbs [ "Maple Mono" 12 ]
  virtualTabs [ "Maple Mono" 12 ]
  files [ "Maple Mono" 13 ]
  statusBar [ "Maple Mono" 12 ]
  tableHeader [ "Maple Mono" 12 ]
  tabs [ "Maple Mono" 12 ]
  preferences [ "Maple Mono" 13 ]
}
```

What the important parts do:

- `behavior.theme` sets the Marta theme. Use the theme `name`, like `"Cita Light"` or `"Cita Dark"`.
- `etty.theme` sets the etty theme. Use the file name without the extension, like `"CitaLight"` or `"CitaDark"`.
- `etty.useMainThemeColors false` tells etty to use its own theme, not the Marta colors.
- `fish_features "no-query-term"` stops fish from sending terminal queries that etty doesn't support.
- The fonts use Maple Mono. Install it first, or change the font name.

## Dark mode

Change both themes:

```
behavior {
  theme "Cita Dark"
}

etty {
  theme "CitaDark"
}
```

## Herdr

The Herdr themes in `herdr-theme` use the same base colors as the etty themes.
