# Lecture 4
1/30/23

*Lecture starts with tmux and text editor testing.*

</br>

When working on a remote session, it will terminate all running programs when we disconnect.
- Def: **tmux** is a terminal multiplexer which allows us to connect/create a persistent shell on a computer.
    - In other words, connect/disconnect from a remote machine while software is running.
    - [**tmux cheatsheet**](https://tmuxcheatsheet.com/): lists commands and shortcuts for tmux.
  
</br>
  
**Text Editors**:
  1) Nano *(main text editor)*
  2) Vi(m) *(hard to use, but [this game teaches you!](https://vim-adventures.com/))*
  3) Emacs **:(**

</br>

Def: A **buffer** or **data buffer** is a region of memory used to temporarily store data while it is being moved from one place to another.
  - *Secretly, it's just an array!*

</br>

*Recommended: Watch ponopto video to set-up VScode for SSH (to linuxlab) and follow along with bash scripting*

</br>

Def: A **shell script** is a text file containing commands for a shell (e.g. bash) to execute.
  - Use # to comment.
  - The first line of the file should contain a special comment called a *shebang* or hashbang.
    - #!/bin/bash -> tells a shell what program to use to interpret the contents of file.
      - bash <script> -> to run bash program.
    - #!usr/bin/env python3 -> first line of a python file so that you can run as an executable.
      - python3 <script> -> to run python program.
  
  
  
