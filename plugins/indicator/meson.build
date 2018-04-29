libindicator_vala_sources = [
  'indicator-capability.vala',
  'indicator-plugin.vala',
]

both_libraries(
  'indicator',
  libindicator_vala_sources,
  dependencies: [
    gnome_pomodoro_lib,
    appindicator_dep,
    libm_dep,
  ],
  install: true,
  install_dir: plugin_libdir,
)

install_data(
  'indicator.plugin',
  install_dir: plugin_libdir,
)

subdir('icons')