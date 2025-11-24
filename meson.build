project(
  'qlementine',
  'cpp',
  version: '1.3.1.0',
  meson_version: '>=1.1',
  default_options: ['cpp_std=c++17'],
)

PROJECT_COPYRIGHT = '© Olivier Cléro, MIT License.'

msvc_flags = ['/MP', '/WX']
gcc_clang_flags = ['-Wall', '-Wextra']

if meson.get_compiler('cpp').get_id() == 'msvc'
  cpp_args = msvc_flags
else
  cpp_args = gcc_clang_flags
endif

qt6 = import('qt6')
qt_dep = dependency('qt6', modules: ['Core', 'Widgets', 'Svg'])

subdir('lib')

if get_option('build_sandbox')
  subdir('sandbox')
endif

if get_option('build_showcase')
  subdir('showcase')
endif