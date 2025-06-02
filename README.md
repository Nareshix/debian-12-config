# debian-12-config

download [cpc](https://github.com/Nareshix/cpc)
```bash
wget https://raw.githubusercontent.com/nareshix/cpc/main/cpc.sh -O ~/.local/bin/cpc && chmod +x ~/.local/bin/cpc
```

## ~/.config/kitty/kitty.conf
```
# themes
include GruvBox_DarkHard.conf
#include Wryan.conf
#include VSCode_Dark.conf

# terminal opacity and blur
background_opacity 1.0
background_blur 1

# advance 
term xterm-kitty

# terminal bell
enable_audio_bell no

# os specific tweaks (Gnome window decoration for wayland)
linux_display_server x11

# font
font_family        SauceCodePro Nerd Font
bold_font          auto
italic_font        auto
bold_italic_font   auto
font_size 12.0

# font size management 
map ctrl+shift+backspace change_font_size all 0

# cursor customization
# block / beam / underline
cursor_shape block
cursor_blink_interval 0
cursor_stop_blinking_after 0
shell_integration no-cursor

# scrollback
scrollback_lines 5000
wheel_scroll_multiplier 3.0

# mouse
mouse_hide_wait -1

# window layout
initial_window_width  1200
initial_window_height 750
remember_window_size  no
window_border_width 1.5pt
enabled_layouts tall
window_padding_width 0
window_margin_width 2
hide_window_decorations no

# window management 
map ctrl+shift+enter new_window
map ctrl+shift+] next_window
map ctrl+shift+[ previous_window

# layout management
map ctrl+shift+l next_layout
map ctrl+alt+r goto_layout tall
map ctrl+alt+s goto_layout stack

# tab bar customization
tab_bar_style powerline
tab_powerline_style slanted
tab_bar_edge bottom
tab_bar_align left
active_tab_font_style   bold
inactive_tab_font_style normal

# tab management
map ctrl+shift+t new_tab
map ctrl+shift+right next_tab
map ctrl+shift+left previous_tab
map ctrl+shift+q close_tab

```


## ~/.config/kitty/GruvBox_DarkHard.conf
```
# Selection Colors
selection_foreground     #ebdbb2
selection_background     #d65d0e

# Window border Colors
active_border_color      #8ec07c
inactive_border_color    #665c54

# Kitty tabs colors 
active_tab_foreground    #ebdbb2
active_tab_background    #458588
inactive_tab_foreground  #ebdbb2
inactive_tab_background  #8ec07c

# Basic color
background               #1d2021
foreground               #ebdbb2

# 16 main colors
color0                   #3c3836
color1                   #cc241d
color2                   #98971a
color3                   #d79921
color4                   #458588
color5                   #b16286
color6                   #689d6a
color7                   #a89984
color8                   #928374
color9                   #fb4934
color10                  #b8bb26
color11                  #fabd2f
color12                  #83a598
color13                  #d3869b
color14                  #8ec07c
color15                  #fbf1c7

# Cursor colors
cursor                   #bdae93
cursor_text_color        #665c54

# Url color
url_color                #458588

```

## ~/.config/fish/config.fish

```
if status is-interactive
    # Commands to run in interactive sessions can go here
end
set fish_greeting

# Your existing aliases
alias mom_legacy_apt_y="sudo apt -y"
alias python="python3"
alias pytohn="python3" # Typo alias
alias clera="clear"    # Typo alias
set -g fish_prompt_pwd_dir_length 0
alias l="ls"
alias s="ls"
alias cle="clear"
alias cl="clear"
alias asdf="clear"
alias asfd="clear"
alias adsf="clear"
alias dsaf="clear"
alias sadf="clear"
alias sl="ls"
alias clea="clear"
alias wasd="clear"
alias celar="clear"
alias lcear="clear"
alias lcea="clear"
alias clrea="clear"
alias clre="clear"
alias intsall="install"
# --- New 'mom' functions (NO ECHO STATEMENTS) ---

function mom_update
    sudo apt update -y
    sudo apt upgrade -y
    sudo apt autoremove -y
end


function mom_install
    if test (count $argv) -gt 0
        sudo apt install $argv -y
    end
end

function mom_remove
    if test (count $argv) -gt 0
        sudo apt purge $argv -y
        sudo apt autoremove -y
    end
end

function mom
    set -l subcommand $argv[1]
    set -l other_args $argv[2..-1]

    switch "$subcommand"
        case update
            mom_update
        case install
            if test (count $other_args) -gt 0
                mom_install $other_args
            else
                # Still good to keep usage instructions if arguments are missing
                echo "Usage: mom install <package1> [package2...]"
                return 1
            end
        case intsall
            if test (count $other_args) -gt 0
                mom_install $other_args
            else
                # Still good to keep usage instructions if arguments are missing
                echo "Usage: mom install <package1> [package2...]"
                return 1
            end

        case remove
            if test (count $other_args) -gt 0
                mom_remove $other_args
            else
                # Still good to keep usage instructions if arguments are missing
                echo "Usage: mom remove <package1> [package2...]"
                return 1
            end
        case '*'
            # Still good to keep an error message for unknown subcommands
            echo "Unknown mom command: '$subcommand'"
            echo "Try: mom update, mom install <package>, or mom remove <package>"
            return 1
    end
end

```



## custom shortcuts
### windows
- close window: alt + 4
### navigation
- Hide all normal: windows super + d
- switch app: super + tab
- swtich windows: alt + tab
- switch window of applicaton: super + `

## gnome tweaks
### startup applicatoin:
  -  chrome
    
## extension
- blur my shell
- clipboard indicator
- dekstop icon (ding)
- just perfection
- no overview at startup
- tiling assistant
- wintile


