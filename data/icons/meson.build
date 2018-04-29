icon_dirs = [
  '16x16',
  '24x24',
  '32x32',
  '48x48',
  '256x256',
  '512x512',
]

foreach i:icon_dirs
  install_data(
    join_paths(i, 'gnome-pomodoro.png'),
    install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'icons', 'hicolor', i, 'apps'),
  )
endforeach

install_data(
  'gnome-pomodoro.svg',
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'icons', 'hicolor', 'scalable', 'apps'),
)
