libgnome_vala_sources = [
  'gnome.vala',
  'gnome-idle-monitor.vala',
  'gnome-plugin.vala',
  'gnome-shell-extension.vala',
]

both_libraries(
  'gnome',
  libgnome_vala_sources,
  dependencies: gnome_pomodoro_lib,
  install: true,
  install_dir: plugin_libdir,
)

install_data(
  'gnome.plugin',
  install_dir: plugin_libdir,
)

install_data(
  'org.gnome.pomodoro.plugins.gnome.gschema.xml',
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'glib-2.0' , 'schemas'),
)

subdir('extension')