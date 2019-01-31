# Tmux cheatsheet
Made by Max Modesto Wallin

## Session
### Create a new session
`tmux new -s session-name # Named session`
`tmux new # Unnamed session`

### Attaching to a session
`tmux a # Attach to first available`
`tmux a #0 # Attach to session with id 0`
`tmux a -t session-name # Attach to session-name`

### Detaching from a session
`<Leader>:detach # Detaches from current session`
`<Leader>d # Detaches from current session`

### Killing a session
`<Leader>:kill-session # Kills the current session`
`tmux kill-session #0 # Kills session with id 0`
`tmux kill-session -t session-name # Kills session named session-name`

## Management
`?` # Show all key mappings

### Session management
`s` # List sessions
`$` # Rename the current session
`j` # Change to the previous session
`k` # Change to the next session
`d` # Detach from the current session

### Windows
`c` # Create a new window
`,` # Rename the current window
`w` # List windows
`%` # Split horizontally
`"` # Split vertically
`h` # Change to the previous window
`l` # Change to the next window
`0` # To 9 select windows 0 through 9

### Panes
`%` # Create a horizontal pane
`"` # Create a vertical pane
`q` # Show pane numbers
`o` # Toggle between panes
`b` # Swap with previous pane
`n` # Swap with next pane
`!` # Break the pane out of the window
`x` # Kill the current pane

### Miscellaneous
`t` # Show the time in current pane

