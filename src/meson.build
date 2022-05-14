silaty_sources = [
  'main.vala',
  'window.vala',
  'application.vala',
]

silaty_deps = [
  dependency('libadwaita-1', version: '>= 1.0'),
]

gnome = import('gnome')

silaty_sources += gnome.compile_resources('silaty-resources',
  'silaty.gresource.xml',
  c_name: 'silaty'
)

executable('silaty', silaty_sources,
  vala_args: '--target-glib=2.50',  dependencies: silaty_deps,
  install: true,
)
