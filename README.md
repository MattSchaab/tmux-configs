# TMUX configurations
## What's this for?
The idea of this repo is to have my tmux configurations ready to go just by cloning this into the config directory.

The config is mostly just bindings for pane switching like vim and a rebind of `<C-b>` to `<C-a>`. Plus a nice colorscheme.

Note: This is meant for unix systems, on Windows machines I used to run it on WSL. But I haven't used windows since 2024.

## Installing
```bash
git clone git@github.com:MattSchaab/tmux-configs.git ~/.config/tmux
```
And then run the install shortcut
```
<C-a> I
```
This config also includes some silly icons, for those to work you need a nerd font installed on the terminal. I'm currently using this one.
```
https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/CascadiaCode.zip
```
If you want to use cht.sh to search for documentation quickly just do
```
<C-a> i
```
This requires to have installed cht.sh which you can find [here](https://github.com/chubin/cheat.sh#installation)

Lastly to remember I'm currently using the colorscheme catpuccin macchiato
```
https://github.com/catppuccin/catppuccin
```

## Usage
Tmux is a terminal multiplexer meaning it manages sessions of multiple terminals.
The bind is a combination you press to trigger actions, since we are in a shell it's hard to have another set of bindings here. I use `<C-a>`

You can create vertical panes with `bind %` and horizontal panes with `bind "`
<img width="49%" alt="vertical panes" src="https://github.com/user-attachments/assets/110d3990-85a4-4248-a86e-7ec4999dbf06" /> <img width="49%" alt="horizontal panes" src="https://github.com/user-attachments/assets/e0bfc5e5-c08d-4732-b11e-39dc600cd8f9" />


You can rebind them with the following in the config
```
bind | split-window -h
bind - split-window -v
```
- Move between panes with `bind HJKL` (I think arrows also work but they suck)
- Close panes `bind x`
- Detatch session `bind d`
- Show sessions `bind s`
- Create a new window  `bind c`
- Move to window `bind tab-number`
- Rename windows `bind ,`

## Sessions
When you run `tmux` you automatically create a new session. If you exit and then run it again you'll start at your home directory again, without the history.
If you want to `attach` to an existing session you can do
```bash
tmux a -t session-name
```
Using just `a` attaches to the last session
```bash
tmux a
```

