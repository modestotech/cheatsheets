# Less cheatsheet
Made by Max Modesto Wallin

	less {filename}

## Navigation
`SPACE || <C-F> # Forward one window`
`<C-B> # Backward one window`
`<C-D> # Forward half window`
`<C-U> # Backward half window`
`_n_j # _n_ lines forward.`
`_n_k # _n_ lines backward.`
`G # Go to the end of file`
`g # Go to the start of file`
`q or ZZ # Exit the less pager`

## Search
`/ # Search for a pattern which will take you to the next occurrence.`
`? # Search for a pattern which will take you to the previous occurrence.`
`n # For next match in forward`
`N # For previous match in backward`

## Other
`F # Simulate tail -f inside less pager`
`ma # Mark the current position with the letter ‘a’,`
`‘a # Go to the marked position ‘a’.`
`&pattern # Display only the matching lines. Return by inputting &<CR>`
`v # Using the configured editor, edit the current file.`
`CTRL+G # Show the current file name with line, byte and percentage.`
