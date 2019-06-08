libusb_dep = dependency('libusb-1.0')
thread_dep = dependency('threads')

if host_machine.system() == 'linux'
  libname = 'hidapi-libusb'
else
  libname = 'hidapi'
endif

hidapi_lib = library(libname,
                     'hid.c',
                     include_directories : inc,
                     dependencies : [libusb_dep, thread_dep])
