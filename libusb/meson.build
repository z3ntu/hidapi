deps = []
deps += dependency('libusb-1.0')

if host_machine.system() == 'linux'
  libname = 'hidapi-libusb'
  deps += dependency('threads')
else
  libname = 'hidapi'
  cc = meson.get_compiler('c')
  deps += cc.find_library('iconv')
endif

hidapi_lib = library(libname,
                     'hid.c',
                     include_directories : inc,
                     dependencies : deps)
