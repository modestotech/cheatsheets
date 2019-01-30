# Vim cheatsheet
Made by Max Modesto Wallin

## Getting help
* : (ex command)
  + *:h :r*
* none (normal)
  + *:h r*
* v\_ (visual)
  + *:h v\_r*
* i\_ (insert mode)
  + *:h i\_CTRL-W*
* c\_ (ex command line)
  + *:h c\_CTRL-R*

## Navigation 
### Vertical navigation 
* `<C-E>`
  + Scroll window down
* `<C-Y>`
  + Scroll window up
* `<C-F>`
  + Scroll one page down 
* `<C-B>`
  + Scroll one page up
* `H`
  + Put cursor in window top
* `M`
  + Put cursor in window middle
* `L`
  + Put cursor in window bottom
* `gg`
  + Put cursor in file top
* `G`
  + Put cursor in file bottom

### Horizontal navigation
#### Word
* `w`
  +	Word forward start
* `e`
  + Word forward end
* `b`
  + Word backward start
* `ge`
  + Word backward end

#### Finding
* `f`
  + Find forward
* `F`
  + Find backward
* `t`
  + Until forward
* `T`
  + Until backward

#### Motions
* `a`
  + All (including motion's surroundings)
* `i`
  + In (inside motion) 

### Special
* `g { movement }`
  + Navigates wrapped text 
* `<C-i>`
  + Traverses through the jumplist (next)
* `<C-o>`
  + Traverses through the jumplist (previous)
* `<C-t>`
  + Jump to `count` older entry in the tag stack
* `v`
  + `v` toggles inclusiveness. 
  + Example "Hello World" when being at the end of the line
       - `dT<Space>` would result in "Hello d"
       - `dvT<Space>` would result in "Hello "
       - This works because T is `exclusive`, see :h t

## Insertion and delete 
### Insert 
* `I`
  + Put cursor in beginning of line and enter insert mode
* `A`
  + Put cursor in end of line and enter insert mode 

### Delete
* `D` 
  + Delete until end of line
* `C`
  + Delete until end of line and enter insert mode

### Insert mode commands
* `<C-O>`
  + Leaves input mode for one command
* `<C-P>`
  + Opens completion menu
* `<C-a>`
  + Insert from . register (dot register)
* `<C-r>`
  + Insert from register, example `<C-r>h` to insert from register h
* `<C-O>`
  + Leaves input mode for one command

### Ex mode completion 
* `<e>`
  + Close popup
* `<C-x><C-n>`
  + Current file (next) 
* `<C-x><C-p>`
  + Current file (previous) 
* `<C-x><C-f>`
  + Filename 
* `<C-x><C-n>`
  + Completion of anything specified by context, set with complete
  + *Explanation:*
      - . (this file)
      - w (other windows)
      - b (other buffers) 
      - u (unloaded other buffers) 
      - t (tags file) 
      - t (included files, such as imports and language specifics) 
* `<C-x><C-l>`
  + Line (context aware)
* `<C-x><C-]>`
  + Tag

## Manipulating text
 * `~`
   + Toggle case of the character under the cursor
 * `g~~`
   + Toggle case of whole line
 * `g~{motion}`
   + Toggle case of the motion
 * `gU{motion}`
   + Change the motion to uppercase
 * `gUU`
   + Change the current line to uppercase
 * `gu{motion}`
   + Change the motion to lowercase
 * `guu`
   + Change the current line to lowercase

## Find and replace 
### In file
* Find
  + Type `\` for forward search or `?` for backward search
      - Prepend search pattern with \v for case insensitive search
* Replace
  + Using sed, `%s/pattern/replace/g`
      - % can be exchanged for any range
      - The g means global, continue search for whole lines

### In project
* Find file
  + Use find command with regex expression and tab through the results, `:find *expression<TAB>`
* Find inside files
  + Using grep command
      - Examples: 
          * `:grep -Fr '.ad' */.css`
              + Finds `class` ad in css files
              + \-F to pass literal string, else it'd be interpreted as regex
              + \-r for recursive search
          * `:grep -ERi '\=\=\= [a-z]{4}\s' */.js`
              + Finds `=== true`
              + -i for case insensitive search
          * `:grep -r --exclude-dir=node_modules 'some pattern' /path/to/search`
              + Finds `some pattern` in `/path/to/search`, excluding the dir node_modules
  + Traversing the results
      - `:cnext` or `ö-q` and `:cprev` or `ä-q` to traverse forward/backward
      - `:copen` and `:cclose` are used to open/close the quickfix list
* Replace inside files (refactor)
  + Use Ack to grep inside project and populate the results in the quickfix list
  + Use `:cdo` to execute a command on the entries in the quickfix list 
  + `update` is like write, but only updates the buffer that's modified'
  + Example: 
      + :Ack foo
      + :cdo s/foo/bar/g | update

## Macros
### Execution 
* `@a`
  + Executes macro a on current line
* `:5,10norm!@a`
  + Executes macro a on lines 5-10@
* `:g/pattern/norm!@a`
  + Executes macro a on matching pattern
* `:%norm!@a`
  + Executes macro a on whole file

## Plugin related
### vim-commentary
* `gcc`
  + Comment/uncomment line
* `gc{motion}`
  + Comment/uncomment motion

### vim-surround
If the opening mark is used, whitespace is added 

* `ds"`
  + Delete surrounding "
* `cs])`
  + Change surrounding ] to )
* `cs]<q>`
  + Change surrounding ] to )
* `ysw(`
  + Add `(` around word and add white space 
* `yss)`
  + Wraps the whole line with `(`

### vim-unimpaired
* `{count}ö<space>`
  + Prepend with {count} line(s)
* `{count}ä<space>`
  + Append with {count} line(s)
* `{count}öe`
  + Move line up {count} line(s)
* `{count}äe`
  + Move line down {count} line(s)

### emmet
* `<C-y>,`
  + Expands emmet before the cursor, for example html:5\_ (\_ is the cursor position)

