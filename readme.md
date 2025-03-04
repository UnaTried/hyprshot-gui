<h1 align="center">Hyprshot GUI</h1>

A simple GTK4-based application for taking screenshots, utilizing <b>Hyprshot</b> under the hood. The design is inspired by **GNOME Screenshot**.

## Features
- Sleek easy-to-use GTK4 interface
- Uses **Hyprshot** for capturing screenshots
- Lightweight and fast

## Interface Preview
![Main Interface](assets/interface.png)

## Dependencies
Ensure you have the following dependencies installed before running the application:

- **Python 3** (minimum required version)
- **python-gobject**
- **GTK4**
- **Hyprshot**

## Installation
**On Arch Linux** run the provided installation script to install all the dependencies and set up the application:

`curl -sL https://raw.githubusercontent.com/s-adi-dev/hyprshot-gui/refs/heads/main/install.sh | sh)`

---
If you are using a different distribution, you need to manually install the required dependencies. After installing the dependencies, you must copy or move the `./src/hyprshot-gui` file to the `/usr/bin/` directory so that it can be executed from anywhere in the terminal.  

Additionally, to integrate **Hyprshot** into your system’s application menu (so it appears in app launchers like `rofi`, `wofi`, or `dmenu`), you need to place the `.desktop` file in `/usr/share/applications/`.  

To do this, run:  

```
sudo cp ./src/hyprshot-gui /usr/bin/hyprshot-gui
sudo cp ./src/hyprshot.desktop /usr/share/applications/hyprshot.desktop
```

## Usage
Once installed, you can launch the app from your applications menu or via the terminal:

```bash
hyprshot-gui
```

## Additional Configuration
For a better user experience, you can configure Hyprland to launch the application in floating mode by adding the following window rule to your Hyprland configuration:
```bash
windowrulev2 = float, title:^(.*Hyprshot.*)$
```

**NOTE**: For users of the install script it gets put at the bottom of the hyprland.conf file!

#### Command Line Options

| Flag | Alias | Description |
|------|-------|-------------|
| `-h` | `--help` | Show help message and exit |
| `-v` | `--version` | Show version information and exit |
| `-o <path>` | `--output-folder <path>` | Set directory to save screenshots |
| `-z` | `--freeze` | Freeze the screen on initialization |
| `-d <seconds>` | `--delay <seconds>` | Set delay before taking a screenshot |
| `--clipboard-only` | | Save only to clipboard |
| `-s` | `--silent` | Do not send notification when a screenshot is saved |
| `-t <ms>` | `--notify-timeout <ms>` | Set notification timeout in milliseconds |

- Example `CLI` Usage
```sh
hyprshot-gui -o ~/Screenshots -d 3 --clipboard-only
```
## Contributing
If you'd like to contribute, feel free to submit pull requests or report issues.

## License
This project is licensed under the [MIT License](./LICENSE).

