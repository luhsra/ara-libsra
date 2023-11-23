includes = []
foreach include_dir : libplatform_include_directories
  includes += ['-I', include_dir]
endforeach

libsra_objs += custom_target('libsra-output.o',
                             input: 'output.cc',
                             output: 'output.cc.o',
                             depfile: 'output.cc.dep',
                             command: clang_cpp +
                                      includes +
                                      ['-I', libsra_include] +
                                      obj_flags +
                                      clang_flags)
subdir('platforms/stm32f103rb')
