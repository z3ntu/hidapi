project('hidapi', 'c')

inc = include_directories('hidapi')

if host_machine.system() == 'linux'
  dep = dependency('libudev')

  src = 'linux/hid.c'
elif host_machine.system() == 'darwin'
  dep = dependency('appleframeworks',
                   modules : ['CoreFoundation', 'IOKit'])

  src = 'mac/hid.c'
elif host_machine.system() == 'windows'
  cc = meson.get_compiler('c')
  dep = cc.find_library('setupapi')

  src = 'windows/hid.c'
endif

hidapi_lib = library('hidapi', src, include_directories : inc, dependencies : dep)
hidapi_dep = declare_dependency(include_directories: inc, link_with : hidapi_lib)
