# tmux

## Table Of Contents
[Configuration](#configuration)

## configuration

** Notes! **

> Example configuration has been installed to:
  /usr/local/opt/tmux/share/tmux

> My tmux config refer to [Hit](git clone https://github.com/gpakosz/.tmux.git).

> Don't forget to replace the following refered 'prefix' in command to real shortcuts(C-b default)

** A TYPICAL TMUX WORKFLOW **

start new project (Session)
```
tmux new -t new-project
```

detach current working session
`prefix d`

list my session
`tmux list`

reattach my working session
`tmux attach -t new-project`

quickly jump between projects without exit tmux
`prefix w`

![prefix w result](https://www.barbarianmeetscoding.com/images/tmux-select-session.jpeg)


In Summary, the basic workflow goes more or less like this:

1 Create session
2 Setup session
3 Work
4 Detach
5 Attach
6 Work
7 To 4)


### Tmux plugin manager : tpm

** Installation **

`git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`

** Append .tmux.conf(or maybe .tmux.conf.local the better) with following snippet **
```
###########################
# Plugins
###########################
# To install plugins:
#   1) Add plugin down here
#   2) Prefix + I to install plugin
# To update plugins:
#   1) Prefix + U
# To remove plugins:
#   1) Remove line down here
#   2) Prefix + ALT + U
# If you're using iTerm2 on a Mac you may need to go to your Profiles, 
# then keys and select that the `option` key should be treated as `Esc+` 
# in order for the `Prefix + ALT + U` combination to work.

# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
# Add more plugins below this line

# Run Tmux Plugin Manager
run '~/.tmux/plugins/tpm/tpm'
```

### Session

### Window

### Pane

**Create a new pane**
vertical: `prefix -`
horizontal: `prefix _`

**Pane navi**
`prefix h/j/k/l`

**Enable pane title status**
`tmux set -g pane-border-status top` or as you will `tmux set -g pane-border-status bottom`

**Rename pane title**
`prefix :select-pane -T <pane_name>`

**Loop Pane when in zoom in mode**

Add this line to your .tmux.conf file:

`bind -r l select-pane -t .+1 \;  resize-pane -Z`

