# Terminal Alacritty Configurations

> Read more at [documentation website](https://alacritty.org/config-alacritty.html)

## Other tools

- `Shell`: [zsh](https://www.zsh.org/)
    - theme: [powerlevel10k](https://github.com/romkatv/powerlevel10k)

- `Text Editor`: [nvim](https://neovim.io/)
    - [current configurations](https://github.com/marcosparreiras/nvim-config)

- `Terminal Multiplexer`:[tmux](https://github.com/tmux/tmux/wiki)
```sh
# ~/.tmux.conf
unbind r
bind r source-file ~/.tmux.conf

set -g default-terminal "tmux-256color"
set-option -ga terminal-overrides ",*:Tc"

setw -g mode-keys vi
set -g mouse on

bind-key h select-pane -L
bind-key j select-pane -D
bind-key k select-pane -U
bind-key l select-pane -R

# Usar o buffer do tmux para enviar para o clipboard do sistema
bind-key -T copy-mode-vi y send-keys -X copy-pipe "xclip -selection clipboard -in"
bind-key -T copy-mode-vi v send-keys -X begin-selection

# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'catppuccin/tmux#v2.1.0'
set -g @catppuccin_window_status_style "rounded"

set-option -g set-clipboard on
set-option -g status-position top
# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'github_username/plugin_name#branch'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
# See documentation at https://github.com/tmux-plugins/tpm
run '~/.tmux/plugins/tpm/tpm'
```

- `psql pager` [pspg](https://github.com/okbob/pspg?tab=readme-ov-file)
```sh
# ~/.pspgrc
theme = 16
border_type = 0
```
