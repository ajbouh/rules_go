package(
    default_visibility = ["//visibility:public"],
)

load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "add.s",
        "asm.go",
        "lib.go",
        "sub.s",
    ],
    deps = ["//examples/lib/deep:go_default_library"],
)

go_test(
    name = "lib_test",
    srcs = [
        "lib_test.go",
    ],
    library = ":go_default_library",
    size = "small",
)

go_test(
    name = "lib_external_test",
    srcs = [
        "lib_x_test.go",
    ],
    args = [
        "-lib_test.buildtime",
        "'05/19/2016 10:30am'",
    ],
    x_defs = {
        "github.com/bazelbuild/rules_go/examples/lib.buildTime": "05/19/2016 10:30am",
    },
    deps = [
        ":go_default_library",
    ],
    size = "small",
)
