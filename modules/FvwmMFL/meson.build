configure_file(
    input: 'FvwmCommandS.in',
    output: 'FvwmCommandS',
    configuration: conf,
    install_dir: fvwm_moduledir
)

executable(
    'FvwmMFL',
    sources: 'FvwmMFL.c',
    dependencies: [all_found_deps],
    include_directories: [lib_includes, fvwm_includes],
    install: true,
    link_with: libraries,
    install_dir: fvwm_moduledir,
)
