src = files(
    'src/animation/WidgetAnimationManager.cpp',
    'src/animation/WidgetAnimator.cpp',
    'src/resources/ResourceInitialization.cpp',
    'src/style/Delegates.cpp',
    'src/style/QlementineStyle.cpp',
    'src/style/EventFilters.cpp',
    'src/style/Theme.cpp',
    'src/style/ThemeManager.cpp',
    'src/tools/ThemeEditor.cpp',
    'src/utils/BadgeUtils.cpp',
    'src/utils/ColorUtils.cpp',
    'src/utils/FontUtils.cpp',
    'src/utils/GeometryUtils.cpp',
    'src/utils/IconUtils.cpp',
    'src/utils/ImageUtils.cpp',
    'src/utils/LayoutUtils.cpp',
    'src/utils/MenuUtils.cpp',
    'src/utils/PrimitiveUtils.cpp',
    'src/utils/RadiusesF.cpp',
    'src/utils/StateUtils.cpp',
    'src/utils/StyleUtils.cpp',
    'src/utils/WidgetUtils.cpp',
    'src/widgets/AboutDialog.cpp',
    'src/widgets/AbstractItemListWidget.cpp',
    'src/widgets/Action.cpp',
    'src/widgets/ActionButton.cpp',
    'src/widgets/ColorButton.cpp',
    'src/widgets/ColorEditor.cpp',
    'src/widgets/CommandLinkButton.cpp',
    'src/widgets/Expander.cpp',
    'src/widgets/IconWidget.cpp',
    'src/widgets/Label.cpp',
    'src/widgets/LineEdit.cpp',
    'src/widgets/LoadingSpinner.cpp',
    'src/widgets/Menu.cpp',
    'src/widgets/NavigationBar.cpp',
    'src/widgets/NotificationBadge.cpp',
    'src/widgets/PlainTextEdit.cpp',
    'src/widgets/Popover.cpp',
    'src/widgets/PopoverButton.cpp',
    'src/widgets/RoundedFocusFrame.cpp',
    'src/widgets/SegmentedControl.cpp',
    'src/widgets/StatusBadgeWidget.cpp',
    'src/widgets/Switch.cpp',
)

headers = files(
    'include/oclero/qlementine/style/QlementineStyle.hpp',
    'include/oclero/qlementine/style/ThemeManager.hpp',
    'include/oclero/qlementine/tools/ThemeEditor.hpp',
    'include/oclero/qlementine/widgets/AboutDialog.hpp',
    'include/oclero/qlementine/widgets/AbstractItemListWidget.hpp',
    'include/oclero/qlementine/widgets/Action.hpp',
    'include/oclero/qlementine/widgets/ActionButton.hpp',
    'include/oclero/qlementine/widgets/ColorButton.hpp',
    'include/oclero/qlementine/widgets/ColorEditor.hpp',
    'include/oclero/qlementine/widgets/Expander.hpp',
    'include/oclero/qlementine/widgets/IconWidget.hpp',
    'include/oclero/qlementine/widgets/Label.hpp',
    'include/oclero/qlementine/widgets/LineEdit.hpp',
    'include/oclero/qlementine/widgets/LoadingSpinner.hpp',
    'include/oclero/qlementine/widgets/Menu.hpp',
    'include/oclero/qlementine/widgets/NotificationBadge.hpp',
    'include/oclero/qlementine/widgets/PlainTextEdit.hpp',
    'include/oclero/qlementine/widgets/Popover.hpp',
    'include/oclero/qlementine/widgets/PopoverButton.hpp',
    'include/oclero/qlementine/widgets/RoundedFocusFrame.hpp',
    'include/oclero/qlementine/widgets/StatusBadgeWidget.hpp',
    'include/oclero/qlementine/widgets/Switch.hpp',
    'src/style/EventFilters.hpp',
)

qrc = files(
    'resources/qlementine.qrc',
    'resources/qlementine_font_inter.qrc',
    'resources/qlementine_font_roboto.qrc',
)

resources = qt6.compile_resources(sources: [qrc])

qt_moc = qt6.compile_moc(headers: headers, dependencies: qt_dep)

qlementine_includes = include_directories('include')

qlementine = library(
    'qlementine',
    sources: [src, qt_moc, resources],
    include_directories: [qlementine_includes, '..'],
    dependencies: [qt_dep],
    cpp_args: '-DHAVE_CONFIG_H',
    install: true,
)

install_headers(headers, subdir : 'include')

pkgconfig = import('pkgconfig')
pkgconfig.generate(
    name : meson.project_name(),
    description : meson.project_name() + ' library',
    version : meson.project_version(),
    libraries : qlementine,
    requires : ['Qt6Core', 'Qt6Widgets', 'Qt6Svg'],
)
qlementine_dep = declare_dependency(
    include_directories: qlementine_includes,
    link_with: qlementine,
)