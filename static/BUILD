# example code is taken from https://github.com/Akagi201/learning-cmake/tree/master/hello-world-lib
# for test only

load("@rules_cc//cc:defs.bzl", "cc_binary")
load("@rules_foreign_cc//foreign_cc:defs.bzl", "cmake")

exports_files([
    "main.c",
])
cc_binary(
    name = "lean4_test",
    srcs = ["main.c"],
    deps = select({
        "//conditions:default": [":lean4"],
    }),
)