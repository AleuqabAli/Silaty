silaty_sources = [
  'main.vala',
  'window.vala',
  'application.vala',
]

blueprints = custom_target('blueprints',
  input: files(
  'window.blp',
  ),
  output: '.',
  command: [find_program('blueprint-compiler'), 'batch-compile', '@OUTDIR@', '@CURRENT_SOURCE_DIR@', '@INPUT@'],
)

silaty_deps = [
  dependency('libadwaita-1', version: '>= 1.0'),
]

gnome = import('gnome')

silaty_sources += gnome.compile_resources('silaty-resources',
  'silaty.gresource.xml',
  c_name: 'silaty',
  dependencies: blueprints,
)

executable('silaty', silaty_sources,
  vala_args: '--target-glib=2.50',  dependencies: silaty_deps,
  install: true,
)
