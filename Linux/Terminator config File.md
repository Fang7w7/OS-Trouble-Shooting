````
[global_config]
  handle_size = 6
  title_transmit_fg_color = "#eeeeec"
  title_transmit_bg_color = "#000000"
  title_receive_fg_color = "#888a85"
  title_inactive_fg_color = "#555753"
  inactive_color_offset = 1.0
  suppress_multiple_term_dialog = True
  title_use_system_font = False
  title_font = Monospace Bold 15
[keybindings]
  split_horiz = <Shift>End
  split_vert = <Shift>Home
  close_term = <Shift>Delete
  page_up_half = <Primary>Up
  close_window = <Primary><Shift>q
[profiles]
  [[default]]
    background_darkness = 0.9
    background_type = transparent
    cursor_color = "#aaaaaa"
    font = Monospace Bold 16
    foreground_color = "#eeeeec"
    show_titlebar = False
    scrollback_infinite = True
    palette = "#000000:#cc0000:#4e9a06:#c4a000:#3465a4:#75507b:#06989a:#eeeeec:#555753:#ef2929:#8ae234:#fce94f:#729fcf:#ad7fa8:#34e2e2:#eeeeec"
    use_system_font = False
[layouts]
  [[default]]
    [[[window0]]]
      type = Window
      parent = ""
      size = 800, 500
      position = 700:100
    [[[child1]]]
      type = Terminal
      parent = window0
[plugins]

````