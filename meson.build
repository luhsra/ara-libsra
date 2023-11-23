project('libsra', 'cpp',
    default_options : ['warning_level=3',
                       'cpp_std=c++17',
                       'buildtype=debugoptimized'])

libplatforms_proj = subproject('ara-libplatforms')
arm_enabled = libplatforms_proj.get_variable('arm_enabled')

if arm_enabled
  ar_cmd = libplatforms_proj.get_variable('ar_cmd')
  clang_c = libplatforms_proj.get_variable('clang_c')
  clang_cpp = libplatforms_proj.get_variable('clang_cpp')
  clang_flags = libplatforms_proj.get_variable('clang_flags')
  obj_flags = libplatforms_proj.get_variable('obj_flags')

  libplatform_link_with = libplatforms_proj.get_variable('libplatform_link_with')
  libplatform_include_directories = libplatforms_proj.get_variable('libplatform_include_directories')

  arm_clang_flags = libplatforms_proj.get_variable('arm_clang_flags')
  arm_ld_flags = libplatforms_proj.get_variable('arm_ld_flags')

  subdir('include')
  subdir('sra')

  libsra_link_with = libsra_ar
  libsra_include_directories = [libsra_include]
else
  libsra_link_with = disabler()
endif
