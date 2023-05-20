# PKGBUILD for d86leader

This is an Arch Linux's PKGBUILD for d86leader's [Wzmach](https://github.com/d86leader/wzmach), a gesture engine for both Wayland and X11.

## Installation

Under clone'd directory:

```sh
makepkg -si
sudo systemctl enable --now wzmach
```

Maybe you need to run before installation:

```sh
sudo usermod -aG input [YOUR USER NAME]
```

## Configuration

Edit /etc/wzmach/config.ron

Look at [d86leader's guide](https://github.com/d86leader/wzmach#configuration) for details.
