libwidget_sources = [
    'Widgets/CheckBox.c',
    'Widgets/HDipstick.c',
    'Widgets/HScrollBar.c',
    'Widgets/ItemDraw.c',
    'Widgets/List.c',
    'Widgets/Menu.c',
    'Widgets/MiniScroll.c',
    'Widgets/PopupMenu.c',
    'Widgets/PushButton.c',
    'Widgets/RadioButton.c',
    'Widgets/Rectangle.c',
    'Widgets/Swallow.c',
    'Widgets/TextField.c',
    'Widgets/Tools.c',
    'Widgets/Tools.h',
    'Widgets/VDipstick.c',
    'Widgets/VScrollBar.c',
    'Widgets/Widget.c',
]

# Todo: could/should this be a shared library?
libWidgets = static_library(
    'Widgets',
    sources: libwidget_sources,
    include_directories: [lib_includes, fvwm_includes],
    link_with: libraries,
    dependencies: all_found_deps,
    install_dir: get_option('libdir'),
)

fvwmscript_sources = [
    'FvwmScript.c',
    'Instructions.c',
    'libyywrap.c',
    'scanner.c',
    'script.c',
]

# C flags for datadir definitions; I think these are defined in config.h
#c_args = ['-DFVWM_DATADIR="@0"'.format(get_option('datadir')),
#          '-DLOCALEDIR="@0"'.format(get_option('localedir'))]

# Build the executable
executable(
    'FvwmScript',
    sources: fvwmscript_sources,
    include_directories: [lib_includes, fvwm_includes],
    dependencies: all_found_deps,
    link_with: [ libraries, libWidgets ],
    #c_args: c_args,
    install_dir: fvwm_moduledir,
)

install_scripts = [
    'Scripts/FvwmScript-BaseConfig',
    'Scripts/FvwmScript-BellSetup',
    'Scripts/FvwmScript-Buttons',
    'Scripts/FvwmScript-Colorset',
    'Scripts/FvwmScript-ComExample.in',
    'Scripts/FvwmScript-Date',
    'Scripts/FvwmScript-FileBrowser',
    'Scripts/FvwmScript-Find',
    'Scripts/FvwmScript-KeyboardSetup',
    'Scripts/FvwmScript-PointerSetup',
    'Scripts/FvwmScript-Quit',
    'Scripts/FvwmScript-ScreenDump',
    'Scripts/FvwmScript-ScreenSetup',
    'Scripts/FvwmScript-WidgetDemo',
]

install_data(
    install_scripts,
    install_dir: fvwm_datadir,
)
