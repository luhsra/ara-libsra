src_files = [
  'serial',
  'debug',
  'sparse',
]

includes = []
foreach include_dir : libplatform_include_directories
  includes += ['-I', include_dir]
endforeach

foreach src: src_files
  libsra_objs += custom_target(src,
                               input: src+'.cc',
                               output: src+'.cc.o',
                               depfile: src+'.cc.dep',
                               command: clang_cpp +
                                        stm32_clang_flags +
                                        arm_clang_flags +
                                        ['-I', libsra_include] +
                                        includes +
                                        obj_flags +
                                        clang_flags +
                                        ['-O2'])
endforeach
