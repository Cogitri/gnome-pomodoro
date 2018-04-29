gnome_pomodoro_vala_sources = [
  'main.vala',
]

posix_dep = meson.get_compiler('vala').find_library('posix')

executable(
  'gnome-pomodoro',
  gnome_pomodoro_vala_sources,
  dependencies: [
    gnome_pomodoro_lib,
    posix_dep,
  ],
  include_directories: incs,
  install: true,
)
