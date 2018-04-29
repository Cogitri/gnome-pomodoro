# We need these to have their first letter be a capital
# letter since we want to install them with those names
# in the end.The dirs in the source directory are lower
# case though, so we got to use to_lower later on
indicator_icons_dirs = [
  'Ambiance',
  'Arc',
  'Radiance',
]

generate_icons_script = find_program('generate-icons')

foreach i:indicator_icons_dirs
  run_command(
    generate_icons_script,
    join_paths(i.to_lower(), 'theme.json'),
  )
  install_subdir(
    i.to_lower(),
    exclude_files: [
      'Makefile.am',
      'theme.json',
    ],
    install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'gnome-pomodoro', 'indicator', i),
    strip_directory: true,
  )
endforeach