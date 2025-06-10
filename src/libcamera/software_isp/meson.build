# SPDX-License-Identifier: CC0-1.0

softisp_enabled = pipelines.contains('simple')
summary({'SoftISP support' : softisp_enabled}, section : 'Configuration')


if not softisp_enabled
    subdir_done()
endif

libcamera_internal_sources += files([
    'debayer.cpp',
    'debayer_cpu.cpp',
    'software_isp.cpp',
    'swstats_cpu.cpp',
])

# halide_dep = dependency('libpisp', fallback : ['libpisp', 'libpisp_dep'])
halide_dep = declare_dependency(
  include_directories: include_directories('/home/stasiu/halide-install-main/include'),
  link_args: ['-L/home/stasiu/halide-install-main/lib', '-lHalide']
)

libcamera_deps += [halide_dep]
