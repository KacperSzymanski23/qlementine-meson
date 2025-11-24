sandbox_name = 'sandbox'

src = files(
    'src/main.cpp',
    'src/SandboxWindow.cpp',
)

sanbox_qrc = files(
    'resources/sandbox.qrc'
)
sandbox_resources = qt6.compile_resources(sources: [sanbox_qrc])

sandbox_exe = executable(
    sandbox_name,
    sources: [src, sandbox_resources],
    dependencies: [qt_dep, qlementine_dep],
)