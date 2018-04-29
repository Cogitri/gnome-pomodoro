project(
  'gnome-pomodoro',
  ['vala', 'c'],
  version: '0.13.4',
)

i18n = import('i18n')
gnome = import ('gnome')

glib_dep = dependency('glib-2.0', version: '>=2.38.0')
gobject_dep = dependency('gobject-2.0', version: '>=2.38.0')
gio_dep = dependency('gio-2.0', version: '>=2.38.0')
gtk_dep = dependency('gtk+-3.0', version: '>=3.20.0')
gdk_dep = dependency('gdk-pixbuf-2.0')
introspection_dep = dependency('gobject-introspection-1.0', version: '>=0.10.1')
peas_dep = dependency('libpeas-1.0', version: '>=1.5.0')
gom_dep = dependency('gom-1.0', version: '>=0.3.0')
gstreamer_dep = dependency('gstreamer-1.0', version: '>=1.0.10')
libcanberra_dep = dependency('libcanberra', version: '>=0.30')
appindicator_dep = dependency('appindicator3-0.1')
sqlite_dep = dependency('sqlite3')

cc = meson.get_compiler('c')
libm_dep = cc.find_library('m')

deps = [
  glib_dep,
  gobject_dep,
  gio_dep,
  gtk_dep,
  introspection_dep,
  peas_dep,
  gom_dep,
  gstreamer_dep,
  libcanberra_dep,
  appindicator_dep,
]

add_project_arguments(
  ['--vapidir', join_paths(meson.current_source_dir(), 'vapi')],
  language: 'vala',
)
# TODO: Can't use meson's dependency/find_library since that'd required a config.pc/libconfig to be installed
# This is a workaround for this
add_project_arguments(
  ['--pkg', 'config'],
  language: 'vala',
)

# We are going to use these variables later on for the plugins
gschema_dir = join_paths(get_option('prefix'), get_option('datadir'), 'glib-2.0', 'schemas')
plugin_libdir = join_paths(get_option('prefix'), get_option('libdir'), 'gnome-pomodoro', 'plugins')
extension_dir = join_paths(get_option('prefix'), get_option('datadir'), 'gnome-shell', 'extensions', 'pomodoro@arun.codito.in')

# TODO: Remove the double quotes from plugins/indicator/extension/config.js.in.
# Right now we have to set the below config values twice because of that,
# the C/Vala code needs these to be quoted (done via `set_quoted`), but
# config.js.in needs them to be unquoted
package_name = 'gnome-pomodoro'
package_string = package_name + ' ' + meson.project_version()
package_version = meson.project_version()
package_bugreport = 'https://github.com/codito/gnome-pomodoro/issues'
package_url = 'http://gnomepomodoro.org'
gettext_package = package_name
extension_uuid = 'pomodoro@arun.codito.in'
package_localedir = join_paths(get_option('prefix'), 'locale')

conf = configuration_data()

conf.set_quoted(
  'GETTEXT_PACKAGE',
  gettext_package,
)
conf.set_quoted(
  'GSETTINGS_SCHEMA_DIR',
  gschema_dir,
)
conf.set_quoted(
  'EXTENSION_UUID',
  extension_uuid,
)
conf.set_quoted(
  'EXTENSION_DIR',
  extension_dir,
)
conf.set_quoted(
  'PACKAGE_LOCALE_DIR',
  package_localedir,
)
conf.set_quoted(
  'PACKAGE_LIB_DIR',
  join_paths(get_option('prefix'), get_option('libdir'), 'gnome-pomodoro'),
)
conf.set_quoted(
  'PACKAGE_DATA_DIR',
  join_paths(get_option('prefix'), get_option('datadir'), 'gnome-pomodoro'),
)
conf.set_quoted(
  'PLUGIN_DATA_DIR',
  join_paths(get_option('prefix'), get_option('datadir'), 'gnome-pomodoro', 'plugins'),
)
conf.set_quoted(
  'PLUGIN_LIB_DIR',
  plugin_libdir,
)
conf.set_quoted(
  'PACKAGE_NAME',
  package_name,
)
conf.set_quoted(
  'PACKAGE_STRING',
  package_string
)
conf.set_quoted(
  'PACKAGE_VERSION',
  package_version,
)
conf.set_quoted(
  'PACKAGE_URL',
  package_url,
)
conf.set_quoted(
  'PACKAGE_BUGREPORT',
  package_bugreport,
)

configure_file(
  output: 'config.h',
  configuration: conf,
)

# Include the just generated config.h
incs = include_directories('.')

subdir('data')
subdir('lib')
subdir('plugins')
subdir('po')
subdir('src')
