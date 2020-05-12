project('boost_sml', 'cpp', 
  version: '1.1.0',
  license: 'boost',
  default_options : ['warning_level=3', 'cpp_std=c++14']
)

boost_dep = dependency('boost')

boost_sml_dep = declare_dependency(
  include_directories: include_directories('include'),
  dependencies : boost_dep
)

if not meson.is_subproject()
  install_headers('include/boost/sml.hpp', subdir: 'sml')
  
  pkgc = import('pkgconfig')
  pkgc.generate(name: 'boost_sml',
    version: meson.project_version(),
    description: 'C++14 State Machine Library'
  )
endif

if get_option('SML_USE_EXCEPTIONS')
  cpp_args = ['-fno-exceptions']
endif

if get_option('SML_BUILD_BENCHMARKS')
  subdir('benchmark')
endif
if get_option('SML_BUILD_DOCS')
  subdir('doc')
endif
if get_option('SML_BUILD_EXAMPLES')
  subdir('example')
endif
if get_option('SML_BUILD_TESTS')
  subdir('test')
endif