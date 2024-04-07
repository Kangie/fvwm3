perl_FVWM = [
    'FVWM/Constants.pm',
    'FVWM/Event.pm',
    'FVWM/EventNames.pm',
    'FVWM/Tracker.pm',
    'FVWM/create-commands',
    'FVWM/create-constants',
    'FVWM/Commands.pm',
]

perl_modfile = [
   'FVWM/Module.pm.in',
]

configure_file(
    input: perl_modfile,
    output: 'Module.pm',
    configuration: perl_config,
    install_dir: perl_config.get_unquoted('FVWM_PERLLIBDIR'),
    install: true
)

install_data(
    perl_FVWM,
    install_dir: perl_config.get_unquoted('FVWM_PERLLIBDIR')
)

perl_fvwm_module = [
    'FVWM/Module/Terminal.pm',
    'FVWM/Module/Toolkit.pm',
]

perl_fvwm_tracker = [
    'FVWM/Tracker/Colorsets.pm',
    'FVWM/Tracker/GlobalConfig.pm',
    'FVWM/Tracker/Makefile.am',
    'FVWM/Tracker/ModuleConfig.pm',
    'FVWM/Tracker/PageInfo.pm',
    'FVWM/Tracker/Scheduler.pm',
    'FVWM/Tracker/WindowList.pm',
]

install_data(
    perl_fvwm_module,
    install_dir: perl_config.get_unquoted('FVWM_PERLLIBDIR') + '/Module'
)

install_data(
    perl_fvwm_tracker,
    install_dir: perl_config.get_unquoted('FVWM_PERLLIBDIR') + '/Tracker'
)
