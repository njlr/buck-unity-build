genrule(
  name = 'mathutils-unity',
  out = 'mathutils-unity.cpp',
  srcs = glob([
    'mathutils/src/**/*.cpp',
  ]),
  cmd = 'cat $SRCS > $OUT',
)

cxx_library(
  name = 'mathutils',
  header_namespace = 'mathutils',
  exported_headers = subdir_glob([
    ('mathutils/include', '**/*.hpp'),
  ]),
  srcs = [
    ':mathutils-unity',
  ],
  licenses = [
    'LICENSE',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'demo',
  srcs = [
    'demo.cpp',
  ],
  deps = [
    ':mathutils',
  ],
)
