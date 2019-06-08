project('hidapi', 'c')

inc = include_directories('hidapi')

if host_machine.system() == 'linux'
  subdir('linux')
  subdir('libusb')
elif host_machine.system() == 'darwin'
  subdir('mac')
elif host_machine.system() == 'windows'
  subdir('windows')
endif

hidapi = declare_dependency(include_directories: inc, link_with : hidapi_lib)

# Stop execution here if we are in a subproject
if meson.is_subproject()
  subdir_done()
endif

subdir('hidtest')

install_headers('')

pkg = import('pkgconfig')
if host_machine.system() == 'linux'

pkg.generate(name : meson.project_name(),
             description : 'C Library for USB/Bluetooth HID device access from Linux, macOS, FreeBSD and Windows.',
             libraries : hidapi_lib,
             version : meson.project_version())
