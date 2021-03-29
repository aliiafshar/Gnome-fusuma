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




