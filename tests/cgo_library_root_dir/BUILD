load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_prefix", "go_test")
load("@io_bazel_rules_go//tests:bazel_tests.bzl", "bazel_test")

go_prefix("github.com/bazelbuild/rules_go/tests/cgo_library_root_dir")

go_test(
    name = "go_default_test",
    size = "small",
    srcs = ["cgo_test.go"],
    library = ":go_default_library",
    tags = ["manual"],
)

go_library(
    name = "go_default_library",
    srcs = [
        "cgo.go",
        "foo.c",
    ],
    cgo = True,
    tags = ["manual"],
)

bazel_test(
    name = "cgo_library_root_dir",
    command = "test",
    target = "//:go_default_test",
)
