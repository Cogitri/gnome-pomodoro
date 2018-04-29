libaction_vala_sources = [
  'action-listboxrow.vala',
  'action-page.vala',
  'actions.vala',
  'action.vala',
  'enums.vala',
  'preferences-page.vala',
]

both_libraries(
  'action',
  libaction_vala_sources,
  dependencies: gnome_pomodoro_lib,
  install: true,
  install_dir: plugin_libdir,
  vala_args: ['--gresources', join_paths(meson.current_source_dir(), 'resources', 'resources.xml')],
)

install_data(
  'actions.plugin',
  install_dir: plugin_libdir,
)

install_data(
  'org.gnome.pomodoro.plugins.actions.gschema.xml',
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'glib-2.0' , 'schemas'),
)