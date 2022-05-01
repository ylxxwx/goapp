load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")
load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix test.hello
gazelle(name = "gazelle")

go_library(
    name = "test.hello_lib",
    srcs = [
        "hello.go",
        "main.go",
    ],
    importpath = "test.hello",
    visibility = ["//visibility:private"],
    deps = [
        "//msg",
        "//vendor/github.com/ylxxwx/goexample/quote",
    ],
)

go_binary(
    name = "test.hello",
    embed = [":test.hello_lib"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "test.hello_test",
    srcs = ["hello_test.go"],
    embed = [":test.hello_lib"],
)
