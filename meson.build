project('nfd', 'cpp', 'c')
# windows implementation is cpp

system = build_machine.system()

dep_includes = include_directories('src/include')
includes = include_directories('src', 'src/include')
deps = []
sources = files(
    'src/nfd_common.c',
    )
if system == 'linux'
  gtkdep = dependency('gtk+-3.0')
  deps += gtkdep
  # TODO check for gtk or zenity
  sources += files(
    'src/nfd_gtk.c',
  )
elif system == 'windows'
  sources += files(
    'src/nfd_win.cpp',
  )
else
  error('System ' + system + ' not implemented yet')
endif

nfd_lib = library(
  'nfd',
  sources: sources,
  include_directories: includes,
  dependencies: deps,
)

nfd_dep = declare_dependency(
  link_with: nfd_lib,
  include_directories: include_directories('src/include'),
  )
