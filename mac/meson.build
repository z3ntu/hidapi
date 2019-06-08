dep = dependency('appleframeworks',
                 modules : ['CoreFoundation', 'IOKit'])

hidapi_lib = library('hidapi',
                     'hid.c',
                     include_directories : inc,
                     dependencies : dep)

