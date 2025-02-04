# Gnome-fusuma config
# Fusuma Configuration for Linux Trackpad (Mac-like Gestures)

This repository contains a custom Fusuma configuration to enable Mac-like multi-touch gestures on Linux using a trackpad. Fusuma is a gesture recognition tool for Linux that allows you to configure custom gestures for your trackpad.

---

## 🚀 Features

- **Swipe Gestures:**
  - **3-Finger Swipe:**
    - **Left:** Navigate forward in history (`Alt + Right`).
    - **Right:** Navigate back in history (`Alt + Left`).
    - **Up/Down:** Open activities overview (`Super` key).
  - **4-Finger Swipe:**
    - **Left/Right:** Switch between workspaces (`Ctrl + Alt + Left/Right`).
    - **Up/Down:** Switch between workspaces (`Super + A/D`).

- **Pinch Gestures:**
  - **In:** Zoom in (`Ctrl + Scroll Up`).
  - **Out:** Zoom out (`Ctrl + Scroll Down`).

---

## 🛠️ Installation

### Step 1: Install Fusuma
Make sure you have Fusuma installed on your system. You can install it using RubyGems:

```bash
gem install fusuma
Step 2: Install xdotool
Fusuma relies on xdotool to simulate keyboard events. Install it using your package manager:

bash
Copy
sudo apt install xdotool  # For Debian/Ubuntu-based systems
sudo dnf install xdotool  # For Fedora
sudo pacman -S xdotool    # For Arch Linux
Step 3: Add Fusuma to Input Group
Add your user to the input group to allow Fusuma to read trackpad events:

bash
Copy
sudo gpasswd -a $USER input
Log out and log back in for the changes to take effect.

Step 4: Copy Configuration File
Clone this repository or copy the config.yml file to your Fusuma configuration directory:

bash
Copy
mkdir -p ~/.config/fusuma
cp config.yml ~/.config/fusuma/
⚙️ Configuration
The config.yml file contains the following settings:

yaml
Copy
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
🖱️ Usage
After setting up Fusuma, you can start it by running:

bash
Copy
fusuma
To run Fusuma in the background, use:

bash
Copy
fusuma -d
