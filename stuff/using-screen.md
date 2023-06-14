## Using Screen
- One way to keep things running in background is to use the `screen` module
- Start a screen, start a process in the screen, and detach from the screen. Straightforward and simple
---
- ### Start a screen
```shell
screen -S someName
# or simply
screen
# this will open a clean window, and everything you do now is inside the screen session
```

- ### Kill a screen
```shell
# if you're done
# do this inside the screen
exit
```

- ### Detach a screen
```shell
# if there's something running, and you want to keep it in background
press Ctrl-A-D
# and you're back to the main session
```

- ### Attach to a screen
```shell
# if you only have one screen
screen -r
# if you gave the screen a name on start
screen -r theName
# if there are multiple screens without names
screen -ls
# multiple screen with times and id's will be listed
screen -r 114514 # or whatever the id is
```

- ### Scroll inside a screen
```shell
press Ctrl-A-[
# Use the arrow keys to navigate
# Use Esc to stop scroll mode
```