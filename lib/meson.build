gnome = import('gnome')

libgnome_pomodoro_vala_sources = [
  'about-dialog.vala',
  'accelerator.vala',
  'aggregated-entry.vala',
  'animation.vala',
  'application.vala',
  'capability-group.vala',
  'capability-manager.vala',
  'capability.vala',
  'desktop-extension.vala',
  'entry.vala',
  'log-scale.vala',
  'notifications-capability.vala',
  'preferences-dialog.vala',
  'presence.vala',
  'screen-notification.vala',
  'service.vala',
  'settings.vala',
  'stats-page.vala',
  'stats-view.vala',
  'stats-day-page.vala',
  'stats-week-page.vala',
  'stats-month-page.vala',
  'timer.vala',
  'timer-action-group.vala',
  'timer-state.vala',
  'utils.vala',
  'window.vala',
]

add_project_arguments(
  '-DGETTEXT_PACKAGE="gnome-pomodoro"',
  language: 'c'
)

libgnome_pomodoro = shared_library(
  'gnome-pomodoro',
  libgnome_pomodoro_vala_sources,
  dependencies: [
    gobject_dep,
    gio_dep,
    gtk_dep,
    peas_dep,
    gom_dep,
    sqlite_dep,
    libm_dep,
  ],
  include_directories: incs,
  version: '0.0.0',
  install: true,
  vala_args: ['--gresources', join_paths('..', 'data', 'resources', 'resources.xml')],
)

gnome_pomodoro_lib = declare_dependency(
  link_with: libgnome_pomodoro,
  dependencies: [
    gobject_dep,
    gio_dep,
    peas_dep,
    gtk_dep,
  ],
  include_directories: [
    # Include gnome-pomodoro.h
    include_directories('.'),
    # Include config.h
    include_directories('..'),
  ],
)