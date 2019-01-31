# Less cheatsheet
Made by Max Modesto Wallin

	less {filename}

## Navigation
`SPACE # Forward one window`
`b # Backward one window`
`d # Forward half window`
`u # Backward half window`
`j # Navigate forward by one line`
`10j # 10 lines forward.`
`k # Navigate backward by one line`
`10k # 10 lines backward.`
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
`&pattern # Display only the matching lines, not all.`
`v # Using the configured editor, edit the current file.`
`CTRL+G # Show the current file name with line, byte and percentage.`
