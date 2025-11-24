showcase_name = 'showcase'

src = files(
    'src/main.cpp',
    'src/ShowcaseWindow.cpp',
)

showcase_qrc = files(
    'resources/showcase.qrc'
)

showcase_resources = qt6.compile_resources(sources: [showcase_qrc])

qlementine_icons_dep = dependency('qlementine-icons')

showcase_exe = executable(
    showcase_name,
    sources: [src, showcase_resources],
    cpp_args: cpp_args,
    dependencies: [qt_dep, qlementine_dep, qlementine_icons_dep],
)