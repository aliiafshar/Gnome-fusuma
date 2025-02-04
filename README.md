# Fusuma Configuration for macOS-like Multi-Touch Gestures on Linux

## Introduction
This repository contains a Fusuma configuration that replicates macOS-style multi-touch gestures on Linux. It uses `xdotool` to map common trackpad gestures to familiar macOS-like actions, such as workspace switching, history navigation, and zooming.

## Requirements
Before using this configuration, ensure you have the necessary dependencies installed:

```bash
sudo apt update && sudo apt install libinput-tools xdotool ruby
sudo gem install fusuma
```

For better performance, install the following optional plugins:

```bash
sudo gem install fusuma-plugin-sendkey fusuma-plugin-tap fusuma-plugin-wmctrl
```

## Configuration
Place the following configuration in `~/.config/fusuma/config.yml`:

```yaml
swipe:
  3:
    left:
      command: "xdotool key alt+Right" # History forward
    right:
      command: "xdotool key alt+Left" # History back
    up:
      command: "xdotool key super" # Activity
    down:
      command: "xdotool key super" # Activity
  4:
    left:
      command: "xdotool key ctrl+alt+Right" # Switch to next workspace
    right:
      command: "xdotool key ctrl+alt+Left" # Switch to previous workspace
    up:
      command: "xdotool key super+a" # Switch to next workspace
    down:
      command: "xdotool key super+d" # Switch to previous workspace

pinch:
  in:
    command: "xdotool keydown ctrl click 4 keyup ctrl" # Zoom in
  out:
    command: "xdotool keydown ctrl click 5 keyup ctrl" # Zoom out
```

## Running Fusuma
To start Fusuma, use the following command:

```bash
fusuma
```

To run it as a background service, use:

```bash
nohup fusuma &
```

For autostart, add it to your startup applications or include it in your `.xprofile` or `.bashrc`.

## Customization
You can modify keybindings according to your preference. Check `xdotool` documentation for more key mappings:

```bash
man xdotool
```

## Troubleshooting
- If gestures are not detected, ensure that `libinput-tools` is installed and `fusuma` has the correct permissions.
- Run Fusuma in debug mode to check logs:

```bash
fusuma -d
```

## License
This configuration is open-source. Feel free to modify and share!

