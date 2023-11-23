libsra_objs = []

subdir('generic')

libsra_ar = custom_target('libsra.a',
                          input: libsra_objs,
                          output: 'libsra.a',
                          command: ar_cmd,
                          build_by_default: true)
