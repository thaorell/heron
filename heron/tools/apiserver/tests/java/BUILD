load("/tools/rules/heron_deps", "heron_java_proto_files")

common_deps_files = [
    "//third_party/java:powermock",
    "@commons_io_commons_io//jar",
    "//third_party/java:mockito",
    "//third_party/java:junit4",
]

apiserver_test_deps_files = \
  common_deps_files + [
    "//heron/tools/apiserver/src/java:heron-apiserver"
  ]

java_library(
    name = "tests",
    srcs = glob(["**/apiserver/**/*.java"]),
    deps = apiserver_test_deps_files,
)

java_tests(
  test_classes = [
    "com.twitter.heron.apiserver.utils.ConfigUtilsTests",
    "com.twitter.heron.apiserver.resources.TopologyResourceTests",
  ],
  runtime_deps = [ ":tests" ],
  size = "small",
)
