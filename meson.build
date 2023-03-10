project('com.github.aharotias2.petitconn', 'vala', 'c', version: '1.0.0')

inc = include_directories('.')

libpetitconn = static_library(
  'petitconn',
  'src/petitconn_repository.vala',
  'src/petitconn_column_set.vala',
  'src/petitconn_gee_utils.vala',
  'src/petitconn_sealed_map.vala',
  'src/petitconn_sql_utils.vala',
  'src/petitconn_value_utils.vala',
  dependencies: [
    dependency('glib-2.0'),
    dependency('libgda-5.0'),
    dependency('gee-0.8'),
    dependency('libxml-2.0')
  ],
  include_directories: inc,
  install: true
)

libpetitconn_dep = declare_dependency(
  include_directories: inc,
  link_with: libpetitconn
)

column_set_tests = executable(
  'petitconn_column_set_tests',
  'tests/petitconn_column_set_tests.vala',
  'src/petitconn_column_set.vala',
  'src/petitconn_sealed_map.vala',
  'src/petitconn_value_utils.vala',
  dependencies: [
    dependency('glib-2.0'),
    dependency('libgda-5.0'),
    dependency('gee-0.8'),
    dependency('libxml-2.0')
  ]
)

abstract_repository_tests = executable(
  'petitconn_repository_tests',
  'tests/petitconn_repository_tests.vala',
  'src/petitconn_repository.vala',
  'src/petitconn_column_set.vala',
  'src/petitconn_sealed_map.vala',
  'src/petitconn_sql_utils.vala',
  'src/petitconn_gee_utils.vala',
  'src/petitconn_value_utils.vala',
  dependencies: [
    dependency('glib-2.0'),
    dependency('libgda-5.0'),
    dependency('gee-0.8'),
    dependency('libxml-2.0')
  ]
)

test('petitconn_column_set_tests', column_set_tests, args: ['1'])
test('petitconn_column_set_tests', column_set_tests, args: ['2'])
test('petitconn_abstract_repository_tests', abstract_repository_tests, args: [])
