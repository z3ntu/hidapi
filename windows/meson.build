cc = meson.get_compiler('c')
dep = cc.find_library('setupapi')

hidapi_lib = library('hidapi',
                     'hid.c',
                     include_directories : inc,
                     dependencies : dep)
