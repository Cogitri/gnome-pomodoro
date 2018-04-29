libdark_theme_vala_sources = [
  'dark-theme-plugin.vala',
]

both_libraries(
  'dark-theme',
  libdark_theme_vala_sources,
  dependencies: gnome_pomodoro_lib,
  install: true,
  install_dir: plugin_libdir,
)

install_data(
  'dark-theme.plugin',
  install_dir: plugin_libdir,
)
