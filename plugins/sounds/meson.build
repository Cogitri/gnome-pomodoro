libsound_vala_sources = [
  'sound-player.vala',
  'sounds-plugin.vala',
]

both_libraries(
  'sound',
  libsound_vala_sources,
  dependencies: [
    gnome_pomodoro_lib,
    libcanberra_dep,
    gstreamer_dep,
    libm_dep,
  ],
  install: true,
  install_dir: plugin_libdir,
  vala_args: ['--gresources', join_paths(meson.current_source_dir(), 'resources', 'resources.xml')],
)

install_data(
  'sounds.plugin',
  install_dir: plugin_libdir,
)

install_data(
  'org.gnome.pomodoro.plugins.sounds.gschema.xml',
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'glib-2.0' , 'schemas'),
)