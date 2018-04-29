dbus_conf = configuration_data()

dbus_conf.set('bindir', join_paths(get_option('prefix'), get_option('bindir')))

configure_file(
  input: 'org.gnome.Pomodoro.service.in',
  output: 'org.gnome.Pomodoro.service',
  configuration: dbus_conf,
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'dbus-1', 'services')
)

i18n.merge_file(
  input: 'org.gnome.Pomodoro.desktop.in',
  output: 'org.gnome.Pomodoro.desktop',
  install: true,
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'applications'),
  po_dir: join_paths('..', 'po'),
  type: 'desktop',
)

i18n.merge_file(
  input: 'org.gnome.Pomodoro.appdata.xml.in',
  output: 'org.gnome.Pomodoro.appdata.xml',
  install: true,
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'metainfo'),
  po_dir: join_paths('..', 'po'),
)

install_data(
  'org.gnome.pomodoro.gschema.xml',
  install_dir: join_paths(get_option('prefix'), get_option('datadir'), 'glib-2.0' , 'schemas'),
)

subdir('icons')
subdir('resources')
subdir('sounds')
