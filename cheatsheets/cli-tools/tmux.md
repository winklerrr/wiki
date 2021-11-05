# tmux

**Reminder:** `<PRE>` stands for the tmux prefix (normally `<CTRL>b` aka. `<C-b>`, maybe changed to `<CTRL>a` aka. `<C-a>`)

## Basics

- **Copy/Paste:** To select text and to paste from clipboard hold `<SHIFT>` while pressing `<LEFT CLICK>` or `<RIGHT CLICK>`
- **Command line:** To enter the tmux command line, hit `<PRE>` and `:`
- `<PRE>?` - show help

## Session management

- `tmux new [-s name]` (`:new`) - create a new session with `name`
- `tmux attach [-t name]` (`:attach`) - attach to the last session or to the session with `name`
- `<PRE>d`, `tmux detach` (`:detach`) - detach from the current session
- `<PRE>s`, `tmux ls` (`:ls`) - list all sessions
- `<PRE>$`, `tmux rename-session [-t name] name` - rename session
- `<PRE>(` - switch to the previous session
- `<PRE>)` - switch to the next session

## Window management

- `<PRE>c` - create new window
- `<PRE>,` - rename current window
- `<PRE>&` - kill current window
- `<PRE>w` - list windows
- `<PRE>f` - find window
- `<PRE>p` - switch to previous window
- `<PRE>n` - switch to next window
- `<PRE>l` - switch to last window
- `<PRE>0..9` - switch to window

## Pane management

### Splitting

- `<PRE>%` - vertically
- `<PRE>"` - horizontally

### Layouting

- `<PRE><SPACE>` - relayout panes
- `<PRE>!` - convert pane into window
- `:join-pane -t name` - join pane into window
- `<PRE>z` - toggle pane zoom

### Switching

- `<PRE>q` - show pane numbers
- `<PRE>q0..9` - switch to pane
- `<PRE>;` - switch to last active pane
- `<PRE>{` - move the current pane left
- `<PRE>}` - move the current pane right
- `<PRE>x` - kill current pane

### Resizing

- `:resize-pane -U 10` - scale pane 10px up
- `:resize-pane -R 10` - scale pane 10px right
- `:resize-pane -D 10` - scale pane 10px down
- `:resize-pane -L 10` - scale pane 10px left
