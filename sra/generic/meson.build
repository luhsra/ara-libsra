src_files = [
  'statistics',
  'print_functions',
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
                                        arm_clang_flags +
                                        arm_ld_flags +
                                        ['-I', libsra_include] +
                                        includes +
                                        obj_flags +
                                        clang_flags)
endforeach
